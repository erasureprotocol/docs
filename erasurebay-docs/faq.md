---
description: Frequently Asked Questions about Erasure Bay
---

# FAQ

### **What is Erasure Bay?**

Erasure Bay is an unstoppable information marketplace built on top of the [Erasure Protocol](https://erasure.world/). You can use Erasure Bay to request any information. The marketplace is fully decentralized and peer-to-peer. Sellers must [put money at stake](https://docs.erasure.world/erasurebay-docs/faq#what-is-a-stake) in order to fulfill a request and Buyers can punish their stake to keep them honest.

### **How do I get started?**

To view existing requests follow [@ErasureBay](https://twitter.com/ErasureBay) on Twitter.

To make or fulfill a request

1. Visit [erasurebay.org](http://erasurebay.org/) and click _**Sign In**_. 
2. Create and connect Authereum account.
3. Create and connect Twitter account.
4. Deposit money into your Authereum wallet.
5. You are ready to go!

[See full walkthrough](new-bay-user-walkthrough.md)

### **What can I request?**

You can request anything that can be expressed in digital form. You can see existing request by following [@ErasureBay](https://twitter.com/ErasureBay) on Twitter to get a sense of what people are requesting. Fulfilling a request requires uploading a file that meets the expectation of the requester. It could be a dataset, a photo that proves a task was completed, a software vulnerability exploit, or anything in between. Video files, image files, text files; the possibilities are almost limitless. Maybe your business wants to host an infosec bounty program. Maybe you want to determine if your intellectual property is being traded on the Dark Web. You can make a request for any information and another user will fulfill it.

### **How do I create a request?**

Requesters will need to obtain an amount of DAI equivalent to the desired reward. For instance, if a user wants to obtain 2GB of Baby Yoda memes and wishes to reward someone 1,000 DAI for doing so, they will need to hold at least 1,000 DAI in their Authereum wallet. Then, you’ll need to designate the amount of DAI required for the Fulfiller to claim the reward, along with the attack ratio you wish to use. Finally, determine the attack period \(in days\) and post your request! Your reward will be staked until your request is fulfilled, or you cancel the request.

### **What is a Stake?** 

A stake is an amount of money attached to a request fulfillment. By staking, sellers have skin in the game to support their claim about the quality of their information. Large stakes imply valuable information, and therefore greater potential compensation. For Erasure Bay, a stake is an amount of USD staked on the Erasure Protocol. It uses DAI stablecoins which has a value pegged to the US Dollar. One DAI is worth one USD. Since DAI is a token, it can be used as a medium of exchange on Erasure Bay, providing clarity on the financial incentives and financial risks of providing bad information.

### **Where does the Reward go?**

### **What is a Punishment?**

Punishments keep sellers honest. When a seller attaches a stake to their fulfillment, they give the right to the requester to burn their stake. This protects requesters since they can now punish fulfillers that provide incorrect or low-quality information. Burning a stake means that the money is deleted forever. A punishment is not free. In order to punish, the requester must burn an proportional amount of money according to the Punishment Ratio. An intuitive way to think about the Punishment Ratio is as how much it costs to punish $1 of the stake. For instance, if the stake is $1,000, the punishment ratio 0.1, and the requester wants to punish for $100, then it will cost the requester $100\*0.1 = $10 to punish $100 from the stake.

### **What is the Punishment Period?**

The Punishment Period is the amount of time, in days, that the Requester has to verify the quality of the information provided by the Fulfiller. Within this window, the Requester may punish the Fulfiller’s stake if they are dissatisfied, but after this period of time, the information included in the fulfillment is deemed to be satisfactory and the stake is released. The Requester can decide to release the stake early if they are satisfied with the submission.

### How do I deposit money?

This can be done with a Debit Card, Apple Pay, or Google Pay by purchasing DAI.

You don’t. In order to create a bounty, you need to obtain DAI. You can do so a number of ways, the easiest being to use Authereum to purchase DAI using Apple Pay or a debit card.

### **Why do I need to connect my Twitter account?**

Twitter is necessary to establish reputation and identity. Since requests and fulfillments are tweeted by the [Erasure Bay Bot](http://www.twitter.com/erasurebaybot), a history is established which other users can review. Reputational risk is one of the punishment/reward mechanisms of Erasure Bay, so an active Twitter account is required.

**Why do you need to have so much access to my Twitter account?**

We only ask for the minimum permissions available. Here’s the [proof](https://developer.twitter.com/en/docs/basics/apps/guides/app-permissions), with a screenshot!

### **What is Authereum?**

With Authereum, you will need to create and connect an account for use within Erasure Bay. Once created, this will act as the primary source for your funds within the Erasure Bay marketplace. As mentioned above, you can use popular applications like Apple Pay to purchase DAI and fund your account/wallet.

Authereum is a non-custodial ERC-20 compliant crypto wallet that was built with web3 primitives in mind. Like any good crypto wallet, you’re in control of your keys \(remember: not your keys not your coins\) and account creation is easy - very similar to what you would experience with MetaMask.

Authereum makes life easier for non-technical users to get on board with Ethereum based applications like Erasure Bay. While on the surface it feels much like a wallet \(and is\), it’s really a larger platform for onboarding users to decentralized apps or DApps behind the scenes.

One of the important differentiators of Authereum versus say MetaMask is they make use of contract based accounts to enable additional key management features; but for the purposes of this FAQ we’ll be sticking to basic wallet use functionality instead. You can read [here](https://medium.com/authereum/authereum-key-architecture-explained-8e0781cf3ea0) if you’d like a more advanced understanding of Authereum’s contract-account architecture.

Authereum is capable of holding many types of crypto tokens including: DAI, BAT, ETH, GNT, and can also hold collectibles if you choose to use it for such purposes.

### **What is DAI?** 

Since crypto is volatile, relative stake value must be stable. DAI provides that stability in the form of a stable 1:1 peg to the US Dollar. DAI also allows for the use of smart contracts, removing the need for trust between parties. Staking and reputational risk are the risk/reward tradeoff and the attack ratio is the mechanism for punishment for providing bad information. [What is DAI?](https://medium.com/mycrypto/what-is-dai-and-how-does-it-work-742d09ba25d6) 

### **How do I obtain DAI?** 

DAI can be purchased directly using Apple Pay or via debit card in Authereum. For more advanced users, Uniswap provides a way to exchange cryptocurrency for DAI.

### How do I make a request for less than a day?

### Can I have multiple accounts?

### **Are there any fees?**

Erasure Bay does not charge any fees to use the marketplace.

### **Does Erasure Bay use NMR?**

Yes. While Erasure Bay uses DAI for payments and staking, NMR is used for burning when a stake is punished. This happens in the background so the user never needs to interact with NMR.

### **How do I know I wont lose my money?**

Rewards are moved into smart contracts as a stake and only released to the Fulfiller at the end of the attack window. No other party except for the Requester can access the DAI tied to a bounty stake. If a Fulfiller provides you bad information, then you can utilize the attack function to burn their stake at the ratio you specified when you created the bounty. Since no third party trust is required, it is impossible for anyone to “steal” your funds. You are always in full control of the bounty.

