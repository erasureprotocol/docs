# Erasure Bay
ErasureBay is a dapp built upon the Erasure protocol. It’s a marketplace for buying/selling information of any kind. It’s Numerai’s demonstration of the power of Erasure to improve the Web itself.

**How it works**
* Post data to storage that no one owns(ex: ipfs)
* Stake money on your claims. Encrypt them, then reveal them, to prove you knew something.
* Sell them under a smart contract that must be enforced.


### State Machine Architecture

Erasure uses shared registries to establish a single source of truth for the Erasure Protocol. So far, the registries developed are:

* Erasure_Agreements: To keep track of Griefing templates.
* Erasure_Posts: To keep track of Feed and Post templates
* Erasure_Users: To keep track of users and their data
* Erasure_Escrows

**Clone Factories**

Using the Spawner library, every item on Erasure is created as a clone of a previously deployed template. We call these Clone Factories. Every clone is also registered in a registry which provides a single source of truth on the status of the protocol.

![](https://i.imgur.com/bEUAp0H.png)

**Staking**

![](https://i.imgur.com/JELJwhJ.png)

**Agreements**

When two parties decide to engage, they begin by staking NMR and agreeing on a set of conditions for punishment. We call this combination of skin in the game and rules of engagement an Erasure_Agreement.

> Griefing is an example of an Agreement which allows two parties to come to a resolution without a third party arbitrator through punishing one another at a cost.

Griefing has two main methods: `_grief()` and `setRatio`
- `_grief` returns the cost of the punishment and is taken form the account of the punisher. Therefore requires appropriate ERC-20 token approval
- `setRatio` Set the grief ratio and type for a given staker. The ratio represents the cost in NMR to burn 1 NMR of the counterparty.

**First example of Griefing is *SimpleGriefing***
> SimpleGriefing agreement allows a staker to grant permission to a counterparty to punish, reward, or release their stake

![](https://i.imgur.com/w0ab7n7.png)

- increaseStake()
Can be called by staker only to increase the stake

- reward()
Called by the counterparty to increase the stake

- releaseStake()
Called by the counterparty to release the stake to the staker

- punish()
Called by the counterparty to punish the staker
```js 
function punish(uint256 punishment, bytes memory message) public returns
(uint256 cost) {
    // restrict access
    require(isCounterparty(msg.sender) || Operated.isOperator(msg.sender),
    "only counterparty or operator");

    // execute griefing
    cost = Griefing._grief(msg.sender, _data.staker, punishment, message);
}
```
`punishment`: amount of NMR (18 decimals) to be burned from the stake
`message`: data to emit as event giving reason for the punishment


**Second Example is *CountdownGriefing***
> CountdownGriefing agreement allows a staker to grant permission to a counterparty to punish, reward, or release their stake until the countdown is completed.
> 
![](https://i.imgur.com/DXy1lte.png)

It behaves similar to SimpleGriefing with an extra touch of a countdown.

`startCountdown`
Called by the staker to begin countdown to finalize the agreement
```js 
function startCountdown() public returns (uint256 deadline) {
    require(isStaker(msg.sender) || Operated.isOperator(msg.sender), "only
    staker or operator");

    // require countdown is not started
    require(isInitialized(), "deadline already set");

    // start countdown
    return Countdown._start();
}
```

**Countdown** makes use of block timestamps to determine start time and end time.
`_start()` Starts the countdown based on the current block timestamp and returns `deadline` which is timestamp of the end of the countdown(current timestamp + countdown length)

Once the countdown is over, the stake can call `retrieveStake()` to retrieve the remaining stake as the agreement has ended.

**CountdownGriefingEscrow**
This contract acts as escrow and allows for a buyer and a seller to deposit their stake and payment before sending it to a CountdownGriefing agreement.

This contract is designed such that there is only two end states: deposits are returned to the buyer and the seller OR the agreement is successfully created.
![](https://i.imgur.com/89jQMVf.png)

We'll go into it's details below

### Step by Step Walkthrough
 
Let's see how erasure bay interacts with erasure protocol
 
**New User Registration**
 
- New User connects to Erasure Client. ErasureClient generates asymmetric encryption keys `PubKey`, `PrivKey`
```js
const keypair = ErasureHelper.crypto.asymmetric.generateKeyPair(sig, salt);
```

- ErasureClient registers user to `Erasure_Users` and uploading it's data
```js
const ethers = require("ethers");
const ErasureUsersArtifact = require("Erasure_Users.json");
const user = keypair.publicKey; // Public Key
const data = 16; //any data

// UserData in bytes
const userData = ethers.utils.keccak256(
      ethers.utils.toUtf8Bytes(data.toString())
    );
// Registering a User
const txn = await ErasureUsersArtifact.from(user).registerUser(userData);
```
***Erasure_Users.sol***
```js
function registerUser(bytes memory data) public {
    require(!_users.exists(msg.sender), "user already exists");

    // add user
    _users.insert(msg.sender);

    // set metadata
    _metadata[msg.sender] = data;

    // emit event
    emit UserRegistered(msg.sender, data);
}
```
Adds user to set of `Users`, sets it metadata and then emits an event saying `UserRegistered`


To remove a user just call method `removeUser`, it removes the user/sender from `_users` set then deletes it's metadata from mapping `_metadata` and finally emits an event `UserRemoved`
```js 
function removeUser() public {
    // require user is registered
    require(_users.exists(msg.sender), "user does not exist");

    // remove user
    _users.remove(msg.sender);

    // delete metadata
    delete _metadata[msg.sender];

    // emit event
    emit UserRemoved(msg.sender);
}
```

To get any user's metadata
```js 
function getUserData(address user) public view returns (bytes memory data) {
    data = _metadata[user];
}
```
**Creating a Post**
A Feed_Factory is a factory contract for managing feeds.  
- Seller first creates a `Feed` template contract from Feed_Factory by calling method `create`

```js 
function create(bytes memory callData) public returns (address instance) {
    // deploy new contract: initialize it & write minimal proxy to runtime.
    instance = Spawner._spawn(msg.sender, getTemplate(), callData);

    _createHelper(instance, callData);

    return instance;
}
```
- It creates a clone of `Feed` template using a nonce, the nonce is same for clones with same calldata. The nonce can also be used to determine the address of the new contract before creation.

_Blob of abi-encoded calldata is used to initialize the template. It returns the instance address of the clone that was created_

- Generates a symmetric encryption key and it's hash
```js
const hexlify = utf8str =>
 ethers.utils.hexlify(ethers.utils.toUtf8Bytes(utf8str));

const nonce = ErasureHelper.crypto.asymmetric.generateNonce()
const symmetricKey = ErasureHelper.crypto.symmetric.generateKey()

// Uses nonce, symmetricKey and above generated asymmetric key's secret
const keyHash =
  ErasureHelper.crypto.asymmetric.secretBox.encryptMessage(symmetricKey,
  nonce, keypair.secretKey)
```

- Encrypt rawData with the symmetric key and gets it ipfs path
```js 
let buf = Buffer.from(rawData);
let dataEncoded = buf.toString('base64');
const encryptedFile = ErasureHelper.crypto.symmetric.encryptMessage(
      symmetricKey, dataEncoded)
const rawHash = await ErasureHelper.ipfs.onlyHash(buf)
const rawDataHash = ErasureHelper.ipfs.hashToHex(rawHash)
```
- Get encryptedData's ipfs path
```js 
const encryptedFileIpfsPath = await ipfs.pinata.pinTextToIPFS(encryptedFile)
```

- Preparing metadata
```js 
const metaData = {
    nonce,
    rawDataHash
    keyHash,
    encryptedFileIpfsPath,
}
```

- Submitting proofHash to our `Feed`
```js 
const proofHash = await
ErasureHelper.multihash({input:JSON.stringify(metaData), inputType:'raw', 
outputType:'digest'})

let confirmedTx = await this.submitProof(proofHash)
```

Feed contract's submitHash method is called to add this proof as hash to feed. 
```js 
function submitHash(bytes32 proofHash) public {
    // only operator or creator of this template can call submit proofHash
    require(Template.isCreator(msg.sender) ||
    Operated.isOperator(msg.sender), "only operator or creator");

    // submit proofHash
    ProofHashes._submitHash(proofHash);
}
```


ProofHashes.sol
```js 
function _submitHash(bytes32 hash) internal {
    emit HashSubmitted(hash); // event emitted whenever submits proofHash
}
```

- Finally submitting metadata to ipfs
```js 
const metadataJsonIpfsPath = await ipfs.pinata.pinJSONToIPFS(metadata)
const metadataHex = ErasureHelper.ipfs.hashToHex(metadataJsonIpfsPath)
```
**Selling a Post**

Once the post is created, it's time to sell.
- Seller creates `Escrow` using CountdownGriefingEscrow_Factory.create() with `calldata` as parameter. This is exactly same as creating a Feed Template as Feed_Factory and CountdownGriefingEscrow_Factory are both factory contracts and method `create` is a factory method.

CountdownGriefingEscrow_Factory.sol
```js 
constructor(address instanceRegistry, address templateContract) public {
    CountdownGriefingEscrow template;

    // here instance type is Escrow
    bytes4 instanceType = bytes4(keccak256(bytes('Escrow')));
    // here initSelector is a Escrow template
    bytes4 initSelector = template.initialize.selector;
    // initializing factory contract
    Factory._initialize(instanceRegistry, templateContract, instanceType, initSelector);
}
```

`CountdownGriefingEscrow_Factory.create(calldata)` will return a Factory Contract with template Escrow.

`_data` is a struct Data of this form
```js
struct Data {
    address buyer;
    address seller;
    uint128 paymentAmount; // amount to be deposited by buyer as payment
    uint128 stakeAmount; // amount to be staked by seller
    EscrowStatus status;
    AgreementParams agreementParams;
}
```
When this escrow template is created, we can provide some params which are then set in _data struct.

`buyer` and `seller` are optional params, if not provide then the first one to stake amount will become seller, the first one to deposit amount will become buyer.

EscrowStatus is an enum, `enum EscrowStatus { isOpen, onlyStakeDeposited, onlyPaymentDeposited, isDeposited, isFinalized, isCancelled }`

- Seller deposits the required stake using `Escrow.depositStake()`


```js 
function depositStake() public {
    // Only seller(the one who created this template) or operator can call
    require(isSeller(msg.sender) || Operated.isOperator(msg.sender), "only
    seller or operator");

    // There should be a seller
    require(_data.seller != address(0), "seller not yet set");

    // deposit stake
    _depositStake();
}

function _depositStake() private {
    require(isOpen() || onlyPaymentDeposited(), "can only deposit stake
    once");

    // declare storage variables in memory
    address seller = _data.seller;
    uint256 stakeAmount = uint256(_data.stakeAmount);

    // Increase the current stake amount
    if (stakeAmount != uint256(0)) {
        Staking._addStake(seller, msg.sender, stakeAmount);
    }

    // emit event
    emit StakeDeposited(seller, stakeAmount);

    // If payment is deposited, finalize the escrow
    if (onlyPaymentDeposited()) {
        _data.status = EscrowStatus.isDeposited;
        finalize();
    } else {
        _data.status = EscrowStatus.onlyStakeDeposited;
    }
}
```

- Buyer deposits the required payment using `Escrow.depositPayment()`
```js 
function depositPayment() public {
    require(isBuyer(msg.sender) || Operated.isOperator(msg.sender),
    "only buyer or operator");

    // restrict state machine
    require(_data.buyer != address(0), "buyer not yet set");

    // deposit payment
    _depositPayment();
}

function _depositPayment() private {
    require(isOpen() || onlyStakeDeposited(), "can only deposit payment
    once");

    // declare storage variables in memory
    address buyer = _data.buyer;
    uint256 paymentAmount = uint256(_data.paymentAmount);

    // Add the payment as a stake
    if (paymentAmount != uint256(0)) {
        Staking._addStake(buyer, msg.sender, paymentAmount);
    }

    // emit event
    emit PaymentDeposited(buyer, paymentAmount);

    // If stake is deposited, start countdown for seller to finalize
    if (onlyStakeDeposited()) {
        _data.status = EscrowStatus.isDeposited;
        Countdown._start();
    } else {
        _data.status = EscrowStatus.onlyPaymentDeposited;
    }
}
```

`Countdown._start()` will start the countdown based on currentblock timestamp, and will return the timestamp at the end of countdown.

- Retrieve buyer's `PubKey` from Erasure_Users
- Computes encryptedSymKey_Buyer = PubKey_Buyer.encrypt(SymKey)
- Computes metadata
- Finalize escrow with creating a griefing agreement `Agreement`

Calling `Escrow.finalize()` 
(1) Will create the agreement
(2) Transfer the stake and deposit to agreement
(3) Start the countdown for agreement  `CountdownGriefing(agreement).startCountdown();`

- Uploads metadata to ipfs
```js 
const metadataJsonIpfsPath = await ipfs.pinata.pinJSONToIPFS(metadata)
const metadataHex = ErasureHelper.ipfs.hashToHex(metadataJsonIpfsPath)
```

- Submitting proofHash to buyer
```js 
const proofHash = await
ErasureHelper.multihash({input:JSON.stringify(metaData), inputType:'raw', 
outputType:'digest'})

let tx = Escrow.submitData(proofHash)
```

Submitting data to the buyer
```js 
function submitData(bytes memory data) public {
    require(isSeller(msg.sender) || Operated.isOperator(msg.sender), "only
    seller or operator");
    
    // Can only submit after finalized
    require(isFinalized(), "only after finalized");

    // emit event
    emit DataSubmitted(data);
}
```

- Retrives
- Computes
**Revealing a Post**
