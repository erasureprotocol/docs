# Official Metrics

### Github Orgs <a id="Github-Orgs"></a>

Erasure and Numerai code is stored in two Github organizations with public and private repositories.

#### [Erasure](https://github.com/erasureprotocol) <a id="erasure"></a>

* [erasure-protocol](https://github.com/erasureprotocol/erasure-protocol): erasure monorepo with smart contracts and tooling
  * [@erasure/abis](https://github.com/erasureprotocol/erasure-protocol/tree/master/packages/abis): npm package with abis and addresses for erasure protocol
  * [@erasure/crypto-ipfs](https://github.com/erasureprotocol/erasure-protocol/tree/master/packages/crypto-ipfs): npm package with utils for erasure protocol
  * [@erasure/testenv](https://github.com/erasureprotocol/erasure-protocol/tree/master/packages/testenv): npm package for local version of the erasure protocol for testing purposes
  * [@erasure/graphql](https://github.com/erasureprotocol/erasure-protocol/tree/master/packages/the-graph): graphql endpoint for querying all erasure protocol data
* [NMR](https://github.com/erasureprotocol/NMR): NMR token smart contracts and audits
* [docs](https://github.com/erasureprotocol/docs): erasure gitbook documentation

#### [Numerai](https://github.com/numerai) <a id="numerai"></a>

* [tournament-contracts](https://github.com/numerai/tournament-contracts): numerai smart contracts for performing custody of user funds.
* [numerox](https://github.com/numerai/numerox): numerai tournament toolbox in python
* [numerai-cli](https://github.com/numerai/numerai-cli): automated workflow for numerai tournament participants
* [numerapi](https://github.com/numerai/numerapi): numerai tournament submission api and queries
* [docs](https://github.com/numerai/docs): numerai gitbook documentation

### Usage Statistics <a id="Usage-Statistics"></a>

This section highlights key usage statistics of the erasure protocol and applications and how to produce them.

#### Data Sources <a id="Data-Sources"></a>

The erasure protocol is built on ethereum and ipfs, thus all its data is publically accessible. Some applications like the Numerai Tournement may operate a backend in order to provide a better product. In those cases, the data will only be public if the application provides an API for queries.

Here are some services for querying the data of the erasure protocol:

* [GraphQL API](https://github.com/erasureprotocol/erasure-protocol/tree/master/packages/the-graph)
* [Google BigQuery](https://ethereum-etl.readthedocs.io/en/latest/google-bigquery/)
* [Dune Analytics](https://hackmd.io/@hagaetc/r1ypkDXKH)

Here are some 3rd party dashboards that track key protocol metrics. Note we cannot guarantee the accuracy of the data provided by these providers, some have been found to be consistantly inaccurate.

* [DefiPulse](https://defipulse.com/erasure)
* [Etherscan](https://etherscan.io/token/0x1776e1f26f98b1a5df9cd347953a26dd3cb46671)
* [CoinGecko](https://www.coingecko.com/en/coins/numeraire)
* [TokenTerminal](https://www.tokenterminal.xyz/protocol/Erasure)
* [Uniswap](https://uniswap.info/token/0x1776e1f26f98b1a5df9cd347953a26dd3cb46671)
* [CoinCodeCap](https://coincodecap.com/project/NMR)
* [FlipsideCrypto](https://coinmarketcap.com/currencies/numeraire/ratings/)

#### Relevant Metrics <a id="Relevant-Metrics"></a>

| Metric | Description | [Erasure Bay](https://erasurebay.org/) | [Erasure Quant](https://erasurequant.com/) | [Numerai](https://numer.ai/) |
| :--- | :--- | :--- | :--- | :--- |
| ESP\_1001 ID | The [ESP\_1001 standard](https://github.com/erasureprotocol/erasure-protocol/blob/release/v1.3.x/standards/ESP_1001.md) provides a template for the metadata submitted to erasure protocol contracts. The `application` field is a string identifier of the application to which this contract instance belongs. | `ErasureBay` | `ErasureQuant` _Application does not currently use ESP\_1001_ | `Numerai` _Application does not currently use ESP\_1001_ |
| Registry activity | Tracking the number of clones registered in each registry \(`Erasure_Users`, `Erasure_Posts`, `Erasure_Escrows`, `Erasure_Agreements`\) provides an estimate of number of users engaging with the protocol across all application. | Erasure Bay is currently operating on `v1.3.x` of the erasure protocol and makes use of all 4 registries. | Erasure Quant is currently operating on `v1.0.x` of the protocol and makes use of `Erasure_Posts` and `Erasure_Agreements` registies. | Numerai is currently operating on `v1.1.x` of the protocol and makes use of `Erasure_Agreements` registry. Note, since numerai performs custody for all tournament participants, all user actions are initiated through this wallet: [0xdc6997b078c709327649443d0765bcaa8e37aa6c](https://etherscan.io/address/0xdc6997b078c709327649443d0765bcaa8e37aa6c) |
| Value at stake | Tracking the total value locked up in the protocol is a sybil resitant way to measure adoption. Since the protocol supports staking with multiple tokens, USD is often used as the base value. See [DefiPulse](https://defipulse.com/erasure) for example. | Erasure Bay currently supports staking with DAI exclusively. DAI is staked when sent to the `CountdownGriefingEscrow` or `CountdownGriefing` contract generated for each request. | Erasure Quant currently supports staking with NMR exclusively. NMR is staked when sent to the `OneWayGriefing` contract generated for each user. | Numerai currently. supports staking in NMR exclusively. NMR. is staked when sent to the `SimpleGriefing` contract generated for each user. The numerai tournament operates part of their system off-chain which means not all stakes are represented on-chain. They’ve built the [numerapi](https://github.com/numerai/numerapi) to enable querying off-chain metrics. Some of the key metrics are available at [numer.ai/nmr](http://numer.ai/nmr). |
| Value burned | Burning NMR is the primary mechanism to punish bad actors on the protocol. Healthy applications will see value burned increase proportionally to the value at stake. | Erasure Bay swaps DAI for NMR on uniswap when performing a burn. Every burn triggers the `Griefed` event on the `CountdownGriefing` contract. | Erasure Quant burns NMR directly. Every burn triggers the `Griefed` event on the `OneWayGriefing` contract. | Numerai burns NMR directly. Every burn triggers the `Griefed` event on the `SimpleGriefing` contract. The numerai tournament operates part of their system off-chain which means not all burns are represented on-chain. They’ve built the [numerapi](https://github.com/numerai/numerapi) to enable querying off-chain metrics. Some of the key metrics are available at [numer.ai/nmr](http://numer.ai/nmr). |
| Value exchanged | This is equivalent to the GDP of the protocol. It is the value which changes hands in exchange for goods and services traded on the protocol. | Erasure Bay uses DAI as the payment currency. Every payment triggers the `PaymentDeposited` event on `CountdownGriefingEscrow` contract. | Erasure Quant uses NMR as the payment currency. Every payment calls the `reward` function on the `OneWayGriefing` contract | Numerai uses NMR as the payment currency. Every payment calls the `reward` function on the `SimpleGriefing` contract. The numerai tournament operates part of their system off-chain which means not all payments are represented on-chain. They’ve built the [numerapi](https://github.com/numerai/numerapi) to enable querying off-chain metrics. Some of the key metrics are available at [numer.ai/nmr](http://numer.ai/nmr). |
| Uniswap Liquidity and Volume | It is expected that NMR liquidity on uniswap will increase with adoption of the protocol. This is because erasure uses [uniswap to burn NMR](https://medium.com/numerai/wheres-nmr-4b411db1e07c). This creates an arbitrage opportunity across uniswap and other exchanges which is covered by higher volume and liquidity. | Uniswap volume produced by Erasure Bay is equivalent to the value burned. | Erasure Quant does not directly use uniswap. | Numerai does not directly use uniswap. However, the app has an NMR purchasing program on uniswap in order to pay rewards. |

### Smart Contracts <a id="Smart-Contracts"></a>

#### Erasure <a id="Erasure"></a>

The Erasure protocol is currently on version `v1.3.0` and composed of 4 registry contracts and more than 20 factory contracts. The protocol is deployed on ethereum `mainnet`, `kovan`, and `rinkeby`.

The 4 active registries are `Erasure_Users`, `Erasure_Agreements`, `Erasure_Posts`, and `Erasure_Escrows`.

The 4 registry contracts remain the same for all major releases of the protocol \(`v1.x.x`\). The factory contracts are changed for every minor releases of the protocol \(`v1.3.x`\). The contract addresses are unchanged for patch releases \(`v1.3.1`\). See [wiki](https://github.com/erasureprotocol/erasure-protocol/wiki) for notes on semantic versioning.

List of Erasure registry and factory addresses and ABIs are maintained in this package: [@erasure/abis](https://github.com/erasureprotocol/erasure-protocol/tree/master/packages/abis)

Note: the factories spawn individual contracts for each user. This means the number of erasure contracts is constantly increasing. You can obtain a list of all contracts of a given type by calling the appropriate registry as such:

```text
let agreements = await Erasure_Agreements.methods.getInstances().call();
```

Many users connect to the protocol through smart contract wallets. This means usage of the protocol is not correctly displayed by etherscan. A complete usage analysis requires transaction tracing or event scanning.

#### NMR Token <a id="NMR-Token"></a>

[Source Code](https://github.com/erasureprotocol/NMR)  
Address: [0x1776e1f26f98b1a5df9cd347953a26dd3cb46671](https://etherscan.io/token/0x1776e1f26f98b1a5df9cd347953a26dd3cb46671)

#### Tournament <a id="Tournament"></a>

All Numerai tournament calls are relayed through the following proxy contracts before reaching NMR / Erasure in order to perform user custody:  
[0x9DCe896DdC20BA883600176678cbEe2B8BA188A9](https://etherscan.io/address/0x9DCe896DdC20BA883600176678cbEe2B8BA188A9)  
[0x1B38819bAB08EF176183D937E21ae1262FE7c337](https://etherscan.io/address/0x1B38819bAB08EF176183D937E21ae1262FE7c337)

