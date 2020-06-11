---
description: 'Date: 17 March 2020'
---

# Erasure Bay Office Hours \#1

![](https://cdn-images-1.medium.com/max/1600/1*R9fKm-fq_smWXAZ9ARHKiw.jpeg)

Numerai expanded their popular office hours video calls with a new topic — Erasure Bay. On Tuesday, 3.17, [Stephane Gosselin](https://twitter.com/thegostep) and [Jonathan Sidego](https://twitter.com/JonathanSidego) opened up a Zoom conference for the community to come chat about the recently launched [Erasure Bay](https://www.coindesk.com/this-usv-backed-startup-has-a-solution-for-buying-information-with-confidence).

For those who couldn’t make it, here’s a recap:

#### Stephane asks Jonathan: why did Numerai build Erasure Bay?

Kicking things off, Stephane asked Jonathan about the genesis of Erasure Bay and how the application came to be. “Sourcing information is a really good use case for staking,” Jonathan explained, “because traditionally if you wanted information from someone, you could only see that information **after** you’ve got it from them. So getting people to stake on it, where you can burn \[the stake\], is a way to start getting reliable information from people you don’t really know too well.”

Where traditionally people would seek out information only from reputable sources, Erasure Bay offers a way to \(in Jonathan’s words\) tap into the long-tail of humans around the world, the “lazyweb of people who know things”. Staking has worked as a quality mechanism for Numerai in the past, as part of their [data science tournament](https://numer.ai/tournament), and in creating Erasure Bay, Numerai is building a generalized version of that mechanism to apply beyond stock market predictions.

#### Along with Erasure Bay, Numerai launched erasure.world

![](https://cdn-images-1.medium.com/max/1600/1*Vs1Y116gXvE5scAKp6oRgA.png)[erasure.world](http://erasure.world)

The Erasure protocol’s new homepage, [erasure.world](http://erasure.world) briefly introduces the protocol and describes what the Numerai team believe are potential use cases.

> Example: staking for online dating where you can burn the other person’s stake if they ghost you, show up late, or turn out to be super rude.

Jonathan neatly summarized the message of the Erasure website and one of the goals of the protocol: “Tying a little bit of money, through staking, to online interactions is a great way to get more honest, real, useful information.”

Stephane added, “There’s this whole vision of a future world where everyone is tied together by economic incentives. It seems like that was the promise of a lot of early DAOs and things, but it never really came true.”

#### How does a hedge fund end up building Erasure Bay?

For all it’s blockchain and data science, Numerai is a hedge fund.![](https://cdn-images-1.medium.com/max/1600/1*vxX7JeXnagaceKpie3Vw1A.png)See?

How does a hedge fund end up building something like the Erasure protocol or Erasure Bay? As Jonathan explained, it actually makes a lot of sense. Numerai has developed a lot of ways to source information, and along the way refined ways to filter that information for quality.

“We tried a lot of ways to get honest predictions out of people, and to make sure Numerai users aren’t overfitting the data we give them to make predictions. So we iterated through a lot of different strategies for getting good information from our users and staking was like, far and away the best way to get people to have skin in the game and provide honest information. It really worked out well for Numerai, and we thought, ‘this could be amazing for the world.’ The fact that other hedge funds and companies haven’t really successfully crowdsourced, and I think we figured out a way of crowdsourcing that the rest of the world would do well to implement in certain ways.”

#### Questions from the community

In advance of the office hours, Numerai shared a Slido link on Twitter and in their [Telegram channel](https://t.me/NMR_Official) for community members to leave questions. After the intro by Stephane and Jonathan, the Q&A began.

**Have you considered the possibility of creating sub-branches of Erasure Bay for different kinds of information? Zero-day attacks, memes, written reports, etc.**

While the team did consider many different applications, Jonathan explained, for the first version they wanted to make something as broad as possible. “v1 is kind of a broad-ish implementation,” he said, “and I think we might keep it broad and not too opinionated for a while and let users discover the different ways of using it.” Jonathan did note that, should strong verticals appear, the team might consider tooling and UX changes to support those verticals.

Stephane added that Erasure Bay is completely open source, and was designed to be easily replicable. A community member could fork Erasure Bay and, while still operating on top of the same protocol and data, re-implement the front end to customize how it presents information to users. Stephane gave the example of filtering out all requests not related to infosec to create an infosec-specific Erasure Bay.

Jonathan also brought up the [Erasure Bay Twitter bot](https://twitter.com/ErasureBay) which Tweets out requests posted to Erasure Bay, noting that it presents an opportunity for people to organize around different keywords or hashtags for specific requests.

**Will we be able to use just MetaMask?**

Currently, making and fulfilling requests on Erasure Bay requires that a user have a Twitter account and an Authereum address. Initially, Authereum was selected because the service could connect to Erasure Bay without requiring a browser plugin or extension, allowing the most people to use the platform across devices \(including mobile\), which was the team’s main goal. Authereum also allows for built in [Wyre](https://www.sendwyre.com/) support, letting users convert fiat to crypto within the application. Jonathan noted that using something like WalletConnect to support other wallets is on their road map, but not in the immediate future.

> It’s an interesting trade-off because on the one hand, lots of people have been using MetaMask for a long time and are familiar with it, and sort of forget how difficult it is to use at first. For a new user that’s completely new to crypto, it seems like a very complicated app where you have to confirm a bunch of things and don’t really know what you’re seeing, and so it’s a more difficult experience for them. And then, when someone’s already familiar with MetaMask, transitioning to Authereum is like, ‘whoa, are we taking a step back here? Username and password? I thought we were just going to do private keys?’ It’s a bit of a balance. We’ll see how things develop, but the goal is to provide the best UX.

> -Stephane on Authereum and MetaMask

**Any new features coming to Erasure Bay?**

Right now the focus is entirely on getting the current iteration as polished as possible. “We’re going to let the users and community lead the way, and we’ll follow them in how they decide to use \[Erasure Bay\] and support features that users want,” Jonathan said, adding, “We’re open to so much feedback at the moment so join our [Rocket Chat](https://community.numer.ai/home) or [Tweet](https://twitter.com/numerai) at us with any ideas you have.”

**Why is it necessary to have a Twitter account to be able to use Erasure Bay? Doesn’t that make it less accessible?**

Jonathan explained that they decided to use Twitter for two reasons:

1. Bootstrap reputation: if someone is making a request for some information and all you can see is the wallet address, there’s no confidence in interacting with that user who might end up griefing you \(burning your stake\) unfairly. If it’s someone fulfilling your request, you don’t know if it’s going to be real information. Attaching a Twitter account lets people see that it’s a real human, they’ve got some followers or a verified check mark.
2. Means to interact with your counter party: when fulfilling a request, you can see who made the request and reach out on Twitter with any questions or possibly negotiate.

[Read more about Twitter in the Erasure Bay docs.](https://app.gitbook.com/@numerai/s/erasure/erasurebay-docs/faq#why-use-twitter)

**Tweets on the Erasure Bay homepage are not the most recent — can you solve that?**

![](https://cdn-images-1.medium.com/max/1600/1*GHURRJ6SG2B2KkYuiA0hAA.png)[Erasure Bay main page](http://erasurebay.org)

The Tweets displayed on the Erasure Bay main page are currently manually updated by the Numerai team. Initially the feed showed the most recent Tweets from the Erasure Bay bot, but the team decided to switch to a curated list of interesting requests while they improve the automation.

**What are the plans for governance of the Erasure protocol for token holders?**

Stephane shared that while governance processes are popular ways for projects to get their communities involved, he hasn’t seen a proposal that seems like a single best way to approach governance. “All of the proposals have a lot of question marks, and it’s a speculative way to design a platform,” he said.

Instead of relying on governance for decentralization, Numerai designed their smart contracts to be completely decentralized from the start, with users opting into any upgrades through the applications they use.

This means that if a new release of Erasure protocol comes out, it’s up to app developers like Jonathan \(developing Erasure Bay\) to recognize if that new release has the features their application wants or needs. As Stephane said, “the protocol developers don’t retain much power; they can ship updates to the chain, but it’s completely up to the users of the Erasure protocol to decide if they want to use a newer version or not.”

**What will the core focus for Erasure Bay be over the coming weeks/months?**

Jonathan and Stephane both agreed that the core focus in the short to medium-term is on growing the community of Erasure Bay users. They want to get people using it to see _how_ they use it, which will inform how they move forward with the project.

Stephane noted that while they want to get as many new users as possible, they want the community to grow organically as use cases emerge. “We have a couple of cool ideas of what we can do,” Jonathan said, “but I don’t want to force a bunch of features on people, I’d rather see what the people want.”

**Will the Numerai team use Erasure Bay for the development of new Numerai products?**

Numerai \(the company\) essentially has two core components: the hedge fund operating with the business model of continuing to run the tournament, and the protocol side focused on empowering people to build their own applications with their own business models \(and using the same primitives as the data science tournament but in different applications\).

The protocol team is incentivized to build applications that demonstrate what the Erasure protocol can do. “Erasure Bay is a great example of this new kind of product that couldn’t exist without Erasure,” Stephane said, “which is why we were really excited to build it ourselves.”

Stephane added that if they come up with other example products like Erasure Bay, they would consider building them, but the goal is for the community to be empowered to build. To that end, next steps are shipping an SDK and open sourcing the Erasure Bay front-end.

**Can you expand on why you decided to use DAI while burning NMR in the background?**

Stephane explained that the decision to use DAI, with NMR in the background, was debated internally for almost a year, and is based on a simple theory: if they want Erasure Bay to be something that’s usable by the masses, payment and staking with a volatile token doesn’t make sense. “You have a completely different risk profile for users that are willing to tolerate \[token\] volatility versus those that are not.” The decision to use a stablecoin for staking comes from a place of working towards broad market appeal.

Stablecoins, however, are not designed to be burned, a necessary component for making the economics of Erasure Bay work. In contrast, NMR has a fixed supply and is meant explicitly for staking and burning, making it an ideal complement to the stablecoin at the foreground of Erasure Bay.

Other than DAI, each stablecoin has some kind of compliance mechanism through whatever jurisdiction is issuing it that allows for withdrawals and cancelling or censoring transactions. DAI, on the other hand, is the only stablecoin currently that doesn’t have those centralized controls, making it the most attractive option from the beginning. Despite the challenges around collateralization DAI is facing, Stephane expressed confidence in the stablecoin’s future \(but noted that they will be ready to switch to a different stablecoin should that be necessary\).

The first Erasure Bay office hours chat was lively and informative —Jonathan and Stephane walked us through a lot of the nuances and details of Erasure Bay not necessarily apparent when using the application, but all of which contribute to the slick UX.

If you haven’t used Erasure Bay yet, check out [this tutorial](https://app.gitbook.com/@numerai/s/erasure/erasurebay-docs/new-bay-user-walkthrough) to set up your accounts and start making requests.

Don’t want to miss the next Erasure Bay office hours? Follow [Numerai](http://twitter.com/numerai) on Twitter or join the discussion on their [Telegram channel](https://t.me/NMR_Official) or [Rocket.Chat](https://community.numer.ai/home).

