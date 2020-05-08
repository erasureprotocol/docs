---
description: Frequently Asked Questions about Erasure Bay
---

# FAQ

### **What is Erasure Bay?**

Erasure Bay is an app for requesting any information in the world. Ask for anything that could conceivable fit in a file. Erasure Bay is fully decentralized and peer-to-peer and built using the Erasure protocol on Ethereum and IPFS.

Someone fulfilling a request must [put money at stake](https://docs.erasure.world/erasurebay-docs/faq#how-do-i-make-a-request) which gives the requester the ability to [punish their stake and their reward](faq.md#what-is-a-punishment) if they are unsatisfied with the information provided.

Anyone can fulfill a request on a first come first serve basis to claim the reward, so make sure your request requires a decent stake.

### **What is Erasure Protocol?**

The Erasure Protocol is a new set of primitives which allows for building new kinds of information applications on the internet. It solves many of the fundamental problems the internet has today. Find out more at [erasure.world](https://erasure.world/).

### **How do I get started with Erasure Bay?**

**To view existing requests:** See [@ErasureBay](https://twitter.com/ErasureBay) on Twitter.

**To make or fulfill a request:**

1. Visit [erasurebay.org](http://erasurebay.org/) and click _**Sign In**_. 
2. Connect your [Authereum wallet](faq.md#what-is-authereum).
3. Connect your [Twitter account](faq.md#why-do-i-need-to-connect-my-twitter-account).
4. [Deposit money](faq.md#how-do-i-deposit-money) into your wallet.
5. You are ready to [make](faq.md#how-do-i-make-a-request) or [fulfill](faq.md#how-do-i-fulfill-a-request) a request!

**Don't like to read?** [Watch video tutorial here](new-bay-user-walkthrough.md)

### **What can I request?**

You can request anything that can be expressed in a file. You can see existing request by following [@ErasureBay](https://twitter.com/ErasureBay) on Twitter to get a sense of what people are requesting.

Fulfilling a request requires uploading a file that meets the expectation of the requester. It could be a dataset, a photo that proves a task was completed, a software vulnerability exploit, or anything in between. Video files, image files, text files; the possibilities are almost limitless. Maybe your business wants to host an infosec bounty program. Maybe you want to determine if your intellectual property is being traded on the Dark Web. You can make a request for any information and another user will fulfill it.

### **How do I make a request?**

Once you've decided what to request, it's time to start filling up your request details:

**Description**

The description is used to tell the world what information you are requesting. You can put anything here, it could be one sentence, or it could be a 100 page document. To get the best response possible, you should describe how you will determine if a response is good or bad.

{% hint style="info" %}
🧙‍♂️**Hint:** To get the best response possible, you should describe how you will determine if a response is good or bad.
{% endhint %}

**Reward**

Before you can place the request, you need to make sure you've [deposited enough money in your wallet](faq.md#how-do-i-deposit-money) to pay the reward amount. For instance, if I requests 100 Baby Yoda memes and am willing to reward someone $1,000 for them, I first need to deposit at least $1,000 in my wallet. ****This reward will be locked in an escrow and added to the stake of the fulfiller when the request is fulfilled.

{% hint style="info" %}
🧙‍♂️**Hint:** If you make a request but do not find anyone to fulfill it, you can cancel it from the request page to get the reward payment refunded.
{% endhint %}

{% hint style="danger" %}
🧞‍♂️**Be careful:** Once a request is fulfilled, you can no longer get the reward back. It is automatically added to the stake of the fulfiller. 
{% endhint %}

**Required Stake**

The required stake is the amount of money a fulfiller needs to attach to their fulfillment. By staking, fulfillers have skin in the game to support their claim about the quality of their information they submitted. Large stakes imply valuable information, and therefore greater potential compensation. Remember, the reward amount is added to the fulfiller's stake as soon a the request is fulfilled. For Erasure Bay, a stake is an amount of USD staked on the Erasure Protocol. It uses DAI stablecoins which has a value pegged to the US Dollar. One DAI is worth one USD.

{% hint style="info" %}
🧙‍♂️**Hint:** If you are not sure what stake amount to ask for, you can always ask for $1B and add a note in your description saying you want to negotiate the details of the detail.
{% endhint %}

{% hint style="danger" %}
🧞‍♂️**Be careful:** Requests can be fulfilled by anyone on a first come first serve basis. Make sure your description is as specific as possible.
{% endhint %}

**Punishment Ratio**

Punishments keep sellers honest. When a fulfiller attaches a stake to their fulfillment, they give the right to the requester to burn their stake. This protects requesters since they can now punish fulfillers that provide incorrect or low-quality information. Burning a stake means that the money is deleted forever. A punishment is not free. In order to punish, the requester must burn an proportional amount of money according to the selected punishment ratio. An intuitive way to think about the punishment ratio is as how much it costs to punish $1 of the stake. For instance, if the stake is $1,000, the punishment ratio 0.1, and the requester wants to punish for $100 from the stake, then it will cost the requester $100\*0.1 = $10.

**Punishment Period**

The Punishment Period is the amount of time that the requester has to verify the quality of the information provided by the fulfiller. Within this window, the requester may punish the fulfiller’s stake if they are dissatisfied, but after this period of time, the information included in the fulfillment is deemed to be satisfactory and the stake is released. The requester can decide to release the stake early if they are satisfied with the submission.

### How do I fulfill a request?

You will need the request's **required stake** amount \(in DAI tokens\) in your Authereum wallet \([How do I  deposit](faq.md#how-do-i-deposit-money)[ money](faq.md#how-do-i-deposit-money)[?](faq.md#how-do-i-deposit-money)\). This will be locked up for the request's specified **punishment period.** During this time the requester can punish your stake if they don't like what you send them. If the requester is satisfied, they will release your stake and your reward to your Authereum wallet.

When you are ready to fulfill a request, hit the **Fulfill** button on the request's page.

#### Public message

This is a message to your requester that will be public to anyone viewing the request page, so don't put anything secret in there. This is useful for explaining or adding any notes to your fulfillment.

#### File

This is the file containing the information that was requested. This will only be viewable by the requester. This can be a file of any format: a text file, a zip containing many files, an image, a video. This is currently limited to 100 megabytes.

When you confirm, your file will be uploaded, the requester will be notified and the punishment period will start. The request will no longer be open to other potential fulfillers.

{% hint style="danger" %}
🧞‍♂️ Make sure you're giving the requester what they are looking for or they might destroy your staked money. If the request is unclear, try reaching out to them on Twitter for clarification.
{% endhint %}

#### Punishment period starts

Once you have fulfilled the request, your stake and the reward are locked together. During the punishment period, the requester may either release the stake and reward to you, or punish you.

Punishing destroys an amount of the combined stake and reward. The requester can destroy your entire stake and reward, or a fraction of it before releasing it to you. The requester has no way of getting their reward back once the request is created.

#### When the punishment period ends

Once the punishment period is over, all un-punished money will be sent to you and no more actions can be taken by anyone on the request.

### **How do I access my wallet?**

You can access your wallet by clicking on your profile name in the top right corner of your screen. This will open up your wallet page where you can see your [DAI balance](faq.md#what-is-dai) and wallet address and access your [Authereum account](faq.md#what-is-authereum).

![](../.gitbook/assets/screenshot-2020-05-08-at-16.51.28.png)

### How do I deposit money?

Erasure Bay uses DAI cryptocurrency \(a stablecoin\) for payments and stakes. [What is DAI?](faq.md#what-is-dai) 

If you do not own any DAI tokens, you can purchase DAI using [Wyre](https://pay.sendwyre.com/), [Coinbase](https://coinbase.com) or a cryptocurrency exchange.

If you already own some DAI, you can transfer it to your [Authereum wallet](faq.md#what-is-an-authereum-wallet) by using the ENS address or the Ethereum address displayed when you click on your username on Erasure Bay.

{% hint style="info" %}
🧙‍♂️**Hint:** Wyre can be unreliable for debit card payments. If you are having issues, try using Apple Pay in Safari on Mac or iOS.
{% endhint %}

{% hint style="info" %}
🧙‍♂️**Hint:** Wyre charges a small fee to convert USD into DAI. Make sure to account for it.
{% endhint %}

### **Is my money safe?**

While nothing in life is risk free, you can rest assured your money is safe. Erasure Bay uses the [Erasure Protocol](faq.md#what-is-erasure-protocol) to secure your funds. Make sure you remember the following: 

* **Wallet Balance:** The money in your wallet is secured by the [Authereum](faq.md#what-is-authereum). 
* **Reward:** The money attached to a request reward is locked up in an escrow and can be fulfilled by anyone on a first come first serve basis. Once the request is fulfilled, the reward is added to the fulfiller's stake and it is no longer possible for the requester to get it back. If no one fulfills the request, the requester can cancel the request to retrieve the reward.
* **Stake:** The money locked up in a stake includes the stake of the fulfiller and the reward of the requester. This stake is locked up in the escrow until the requester releases it or the [punish period](faq.md#how-do-i-make-a-request) is over. Be careful, the requester can burn the stake at any time during the punish period according to the [punish ratio](faq.md#how-do-i-make-a-request) if they are unsatisfied with the fulfillment.

### **Why use Twitter?**

Twitter fulfills a few purposes on Erasure Bay:

1. Build trust with participants by associating an identity to your requests
2. Discover content through our bot [@ErasureBay](https://twitter.com/erasurebay)
3. Receive notifications when someone interacts with your request or fulfillment
4. Allows for communication, like the negotiation of terms

We ask for the [minimum OAuth permissions](https://developer.twitter.com/en/docs/basics/apps/guides/app-permissions) available to establish a provable link between your Authereum wallet and your Twitter account. This only happens once.

### **What is Authereum?**

**Authereum is a cryptocurrency wallet like MetaMask**. Unlike MetaMask it does not require a browser addon, so works on any device like your phone or tablet. You can use your Authereum account to [deposit money](faq.md#how-do-i-deposit-money) to Erasure Bay.

Authereum is a non-custodial wallet which means no one but you has access to your money. Authereum makes it easy for non-technical users to keep their currency secure while providing advanced features. Read [here](https://medium.com/authereum/authereum-key-architecture-explained-8e0781cf3ea0) for a more advanced understanding of Authereum’s contract-account architecture.

Erasure Bay does not currently support MetaMask.

{% hint style="danger" %}
🧞‍♂️**Be careful:** Your Authereum account secures all the money and valuable information you submit to Erasure Bay. Make sure to choose a secure password and store it with a password manager like [1password](https://1password.com/) or [lastpass](https://www.lastpass.com/). For more tips on keeping your wallet secure, see the [Authereum blog](https://link.medium.com/maY63KJmK4).
{% endhint %}

### **What is DAI?** 

**A DAI token is a digital representation of one US dollar.** It is a stable cryptocurrency that runs on the [Ethereum blockchain](https://docs.ethhub.io/ethereum-basics/what-is-ethereum/) whose price aims to stay at roughly 1 USD per DAI.  
  
DAI's value is backed by cryptocurrency collateral, mainly ether, the currency of the Ethereum blockchain. DAI maintains its stability to the dollar by aligning market incentives among thousands of global actors. DAI allows for the use of smart contract platforms like the [Erasure Protocol](faq.md#what-is-erasure-protocol). 

You can learn more about stablecoins like DAI [here](https://blog.dharma.io/what-is-a-stablecoin/).

### **Does Erasure Bay use NMR?**

**Yes**. While Erasure Bay uses DAI for payments and staking, it [burns up NMR in the background](https://medium.com/numerai/wheres-nmr-4b411db1e07c?source=friends_link&sk=1c1553ec198e3b486b9a40a39d2e4503).

### **Are there any fees?**

**Erasure Bay does not charge any fees**. This is possible through the magic of crypto-economic incentives. More on this soon.

### Troubleshooting

Erasure Bay has been most extensively tested in **Google Chrome**, though works in **Firefox** and **Safari** \(including mobile\). If you are using **Brave**, make sure Brave Shield is turned off.  
  
If you are experiencing issues signing in, try visiting [Authereum.com](https://authereum.com) and logging out and back in again.

Authereum requires cross-site cookies to be enabled to work correctly. Learn how here: [https://docs.authereum.com/browser-compatibility](https://docs.authereum.com/browser-compatibility)

### Still need help?

Contact us on [RocketChat](https://community.numer.ai/channel/erasure/) / [Twitter](http://twitter.com/numerai) / [Telegram](http://t.me/NMR_Official).

