---
description: 'Date: 31 March 2020'
---

# Erasure Bay Office Hours \#2

![](https://cdn-images-1.medium.com/max/1600/1*bQAwhNT1CEwmeV6OqUUSzQ.jpeg)

March was a big month for Erasure: the protocol passed a significant growth milestone and saw the launch of Erasure Bay, the latest application built on Erasure by Numerai \(the first being [Erasure Quant](https://erasurequant.com/)\). 

![](https://cdn-images-1.medium.com/max/1600/1*qga1Fj7YIugXJ9oZMkGoZA.png)

Read the [full post on Medium](https://medium.com/numerai/erasure-bay-launch-1m-staked-community-ama-cc074324b23d) \| [Subscribe](https://upscri.be/r65sa5) to get updates in your inbox

**Erasure Bay is Live**

Stephane highlighted some of the most interesting requests users made since Erasure Bay launched earlier in the month:

Stephane noted the diversity of requests, ranging from [Jonathan’s](https://twitter.com/JonathanSidego) request for the full video of Epstein’s deposition, dev communities to find hard-to-Google information, and requests for art.

![Art from Erasure Bay](https://cdn-images-1.medium.com/max/1600/1*NwZkfI-4TRpIYYGtUS0thg.jpeg)

Next, Stephane broke down the relationship between NMR and DAI on Erasure Bay: when a stake or reward is burned, the DAI is automatically swapped for NMR using Uniswap. The resulting NMR is burned, permanently taking it out of circulation. From etherscan:![](https://cdn-images-1.medium.com/max/1600/1*bTGa4lIgQTiF9p9FRmmvHw.png)[The first burn on Erasure Bay.](https://etherscan.io/tx/0x0cadb065c62bb3eb948a07d63999ba9356845a0cdb07935fb62d98f26025127f)

> “We’re really excited that momentum is starting to pick up. We’re seeing people track requests as they come in; we’re seeing fulfillments happen quite quickly which we’re thrilled to see. I expect we’ll see more and more burns as the platform grows, which is really exciting, too.” — Stephane

NJ added that, in the days leading up to Office Hours, she noticed an increasing number of Twitter users unfamiliar to the Numerai community tagging the [Erasure Bay bot](https://twitter.com/ErasureBay) in threads having nothing to do with Numerai or the topics most commonly associated with the company. “That kind of early growth is really exciting to see,” she said.

> “This is something we should tap into. There’s so many things on Twitter making claims or asking for things. A lot of these “ask lazyweb” questions get bad answers or troll answers. But if they ask on Erasure Bay instead and retweeted it, they would be guaranteed to get much higher quality responses. I think it’s really cool to @ them and tell them about the product.” — Stephane

**$1 million dollars staked on Erasure**

Around March 20th, the Total Value Locked \(USD\) in Erasure surpassed $1 million.![](https://cdn-images-1.medium.com/max/1600/1*NtZlQV_zKRHuZlmqWwiIbw.png)Pictured: Richard on March 20th \(probably\)

The [Erasure protocol](https://erasure.world/) lies beneath the [Numerai tournament](http://numer.ai/tournament), [Erasure Quant](http://erasurequant.com), and [Erasure Bay](http://erasurebay.org), powering the staking mechanisms for these applications. Stephane explained that the continuing growth of value locked in Erasure is driven by multiple factors: data scientists performing well in the tournament, Erasure Bay launching, and the market performance of the NMR token.![](https://cdn-images-1.medium.com/max/1600/1*JUjtGtD2rkZE62Zb2stXBQ.png)Chart from [DeFi Pulse](https://defipulse.com/erasure)

The amount staked on Erasure is a good metric for gauging total user activity for applications built on the protocol because, as Stephane explained, it encompasses a variety of different activities, such as a data scientist’s stake on their model and requests for information on Erasure Bay, but also shows true skin in the game from the users. “That’s what we’re trying to optimize for with Erasure,” Stephane said.

**Erasure Bay community AMA**

The final monthly update section Stephane walked us through was about the [Erasure Bay Office Hours \#1](https://medium.com/numerai/erasure-bay-office-hours-1-3c7b63b13e7d) and the feedback from the community since Erasure Bay launched.

He said:

> “The [update for February](https://medium.com/numerai/rallying-the-numerati-80d321ea2dd9) was to try to get the community more engaged because we really want Erasure Bay to be a product for the community and owned by the community such that the community owns the roadmap.”

#### Questions from Slido

**I don’t get it — in the simplest terms, can you explain what’s the point of all this?**

Jonanthan put it simply: Erasure Bay is a place where you can request any information. People visit [the website](http://erasurebay.org) and [make a request](https://app.gitbook.com/@numerai/s/erasure/erasurebay-docs/new-bay-user-walkthrough) for anything that can be delivered as a file such as a video, a spreadsheet, a data set, or a graphic.

The requester locks money in a smart contract as a reward for the information. Anyone can claim that reward by fulfilling the request. Submitting a file to a request, however, requires the fulfiller to stake their own money as well, to guarantee confidence in their file; both parties have to have skin in the game. Once the requester has reviewed the file, if they’re happy with it they release the reward and the fulfiller’s stake.

But, if the requester isn’t satisfied with the file, maybe it’s not accurate or detailed enough, the requester can grief their money, burning all or part of what’s at stake. “It’s a way of crowdsourcing information from anyone in the world,” Jonathan said, “and it can be any kind of information.”

He continued: “The basic mechanism that can be generalized is people stake money and if you’re not happy with what they’ve staked, you can destroy their money. Or if you are, you release the reward to them.”

To get an idea of what’s already been requested, visit the [Erasure Bay Twitter account](http://twitter.com/erasurebay).

> “There’s so much that someone, somewhere in the world knows but there isn’t a way to credibly source it from them. Getting people to stake on it is a way to suck information out of the earth.” — Jonathan

![](https://cdn-images-1.medium.com/max/1600/1*yD0tEDMaVQf076uV7tG7eQ.png)

**I believe there are a lot of people who land on Erasure Bay and are excited about it, but also scared about the risk of putting money into something. Is there any way to provide a greater guarantee that this is a system that works? What kind of features did Numerai build to provide security for these users?**

The staking mechanism is designed to offer this kind of protection. Using the example of a recent [request for CT scans of COVID-19 patient lungs](https://twitter.com/ErasureBay/status/1244798210192756737) by a data scientist hoping to build models, Jonathan explained how asking for this information on Twitter opens the question up to the world which may result in a high volume of responses, but trash responses create so much noise that the requester may be unable to separate garbage from gold.

Erasure Bay requires that anyone who responds put money down on their response, and if it’s not good, the requester can destroy that money. Because of this, the people who respond are overwhelmingly more likely to not be trolls or providing poor quality information.

> “Skin in the game prevents bad actors. That’s the whole purpose of the \[Erasure\] protocol and why we don’t need a centralized party to tell who’s right and who’s wrong. The users have all of the tools they need to do it themselves.” — Stephane

**Will there be a chance for users who don’t have enough capital to stake to participate and make money using this platform?**

Looking at the [Erasure Bay Twitter bot](http://twitter.com/erasurebay) for what’s already been requested, many of the requests are in the $5-$10 range — coffee money. Jonathan mentioned a user who recently fulfilled a request earned their first DAI ever and was excited to use them. “I think this is a fun way for people to earn their first bit of crypto online,” he said, going on to add, “It will never be free, or not require a stake amount, because that defeats the point of the whole thing — you need some sort of skin in the game.”

**How does Numerai expect the amount staked, specifically on Erasure Bay, to grow over time?**

\*\*\*\*![](https://cdn-images-1.medium.com/max/1600/1*Jn6NNibjgdD0HjeuDyhzAg.gif)That’s the $2 million question

Jonathan explained that right now, one of the biggest challenges is the friction that exists around people getting and using cryptocurrencies. He pointed out that many people aren’t comfortable using cryptocurrencies to interact with products like Erasure Bay yet. “That’s something we’re really focused on,” he said, “getting people to not be afraid to use \[Erasure Bay\].” This focus on user experience is a contributing factor to why the team built on Ethereum, and why the first token used for Erasure Bay is DAI — to make the platform as neutral and accessible as possible.

_For more on why Erasure Bay uses DAI, see_ [_Erasure Bay Office Hours \#1_](https://medium.com/numerai/erasure-bay-office-hours-1-3c7b63b13e7d)_._

“I think that’s where we’re going to find more growth,” Jonathan said, “making this more usable to the person on the street. I think it has a broad application beyond just crypto people.”

Stephane added that \(at the time of the Office Hours\), Erasure Bay was about two weeks old and already had around $10,000 staked.![](https://cdn-images-1.medium.com/max/1600/1*WDhF-tnn3FcbTrHWW3nL5Q.png)ACTUALLY Stephane, it was $10.063k on March 31, the day of Office Hours. Chart from [DeFi Pulse](https://defipulse.com/erasure).

**Any updates on the Erasure Grant? The** [**$1 million grant announced**](https://medium.com/numerai/1-million-nmr-giveaway-6f2fcbc91d29) **in 2019?**

“The short answer,” Stephane said, “is that we haven’t sponsored any other teams to build applications on top of the protocol yet.” Though Stephane said this was due to multiple factors, the primary reason he cited is absence of tooling available to fully empower any other teams. In reviewing the proposals Numerai received through the grants program, they noticed a large number of the projects replicated a significant amount of work that Numerai had already done. They wanted to make sure that each grant application wouldn’t have to start from scratch and do redundant development work.

Numerai used $75,000 to sponsor [a hackathon with CoinList](https://coinlist.co/build/erasure/votes) to help develop new tooling for Erasure, one of the resulting projects being an [Erasure SDK](https://erasure-docs.robinthomas2591.now.sh/index.html) that the team used to build Erasure Bay. Stephane added that they plan to release the SDK to the public in the near future.

> “The first step is to develop the tooling to make sure that people can be effective in building applications.” — Stephane

Once the Numerai team feels that the available tooling is sufficiently robust, they will revisit the grants program. Stephane said that the intention is to make the program entirely decentralized, so they’re exploring options to make it permissionless, removing any kind of application process. “Anyone can start building on the protocol,” he said, “and depending on the amount of usage, the amount of burn they’re able to generate through their app, they’ll get a proportion of the grant money automatically.”

**I cannot wait for the Tinder-like application — I think that’s my best chance of becoming rich.**![](https://cdn-images-1.medium.com/max/1600/1*VE3w1YpG1HdXCgBl84N2Rw.jpeg)Erasure Bae ♥️ coming soon \(maybe\)

The idea of a dating application powered Erasure Bay was first mentioned on the [Erasure website](http://erasure.world) and serves as a strong example of a use case beyond requests that look similar to traditional job board posts.![](https://cdn-images-1.medium.com/max/1600/1*UNUt0ZzVcDo2CB7qodyKRA.gif)Jonathan is also a big fan of the idea.

“Imagine this,” Jonathan said, full of enthusiasm, “imagine a dating application where every time you swipe right on someone, you stake $5. That way, when a girl sees that you’ve swiped on her, she knows you’re not playing around and swiping a million times. You’ve shown a bit of intent.”

In this example, the girl agrees to a first date, but requires her suitor to stake $500. “You know that person won’t be late,” Jonathan said, “because if they’re five minutes late, the girl can delete their money off the face of the planet.”

Using the Erasure Bay model, with money at stake, the girl has some degree of protection against unseemly, aggressive, or otherwise unpleasant behavior. “I think it will fix dating for everyone forever.”

**From chat:** What prevents the girl from deleting even if the date isn’t late \(in this context\)?

Without skipping a beat, Jonathan replied, “Nothing prevents them from doing that.” He explained that the way Erasure Bay is set up, burning a user’s stake is not free: when a user creates a request, a punishment ratio is set. This determines how expensive it would be for the requester to destroy the fulfiller’s stake.![](https://cdn-images-1.medium.com/max/1600/1*x1SwRt80ElxXw49sp4yYAA.png)Making a request on [Erasure Bay](http://erasurebay.org)

A similar approach can be used for a dating platform, meaning it wouldn’t be free for the girl to burn her suitor’s stake. The griefing mechanism is a central component of Erasure Bay — as Jonathan said earlier, it ensures both people have skin in the game. This provides a real economic incentive for both parties to behave honestly.

Jonathan explained that on Erasure Bay right now, a requester can arbitrarily set the punish ratio so that it favors whoever has a stronger reputation or has the most trust in the relationship. “If I’m trying to prove that I would be a really good date,” Jonathan explained, “I would set the ratio in \[the girl’s\] favor.” By making it so easy for his date to burn his stake, Jonathan is sending a strong signal in his confidence that he will be a perfect gentleman and that she will have a good time.

**Is there a concept of ‘reputation’ that is built up over time in Erasure Bay?**

“Not explicitly at the moment,” Jonathan said, “reputation is the immutable ledger of griefs and fulfillment interactions you’ve had.” By looking at a user’s history on the [Erasure Bay Twitter bot](http://twitter.com/erasurebay) feed, or looking through their address history on an explorer like etherscan, someone could easily determine whether or not the user is a bad actor based on their ratio of successful fulfillments to times they’ve been griefed. “But it is something we’ve thought about,” Jonathan said.

**What about using the Erasure protocol for establishing a peer-reviewed paper repository in which reviewers are paid \(or potentially punished\) by editors?**

“I think this is a really great idea,” Stephane said. “This taps into this narrative that we really believe in on [erasure.world](http://erasure.world). We really think these mechanisms that we’ve built generalize into any marketplace where there’s information asymmetry between the buyers and the sellers. There are so many inefficiencies in the current systems that are tied directly to the inability for the buyer to make a credible threat against the seller.”![](https://cdn-images-1.medium.com/max/1600/1*ytV_-rnBwB0uN6VfqsDbcQ.jpeg)Richard slaps roof of Erasure: “This bad boy can fit so much damn grief.”

Stephane shared that for those interested in the game theory behind how this works, reading about [asymmetric game theory](https://www.nature.com/articles/s41598-018-19194-4) or [principal-agent problems](https://www.jstor.org/stable/258191?seq=1#metadata_info_tab_contents) are good places to start. Many of the mechanics comprising these types of games can be solved by introducing staking and burning mechanisms like those used on Erasure Bay, Erasure Quant, and in the Numerai tournament.

_To learn more about why griefing works, you can also read_ [_The neural basis of altruistic punishment_](https://www.ncbi.nlm.nih.gov/pubmed/15333831/)_, de Quervain et all, 2004._

“What we really want to do is make it as easy as possible for people to build these applications, experiment with different use cases, and we’ll add those to the [erasure.world](http://erasure.world) website and convert the site into a gallery of ideas,” Stephane said. “The goal is to display the range of use cases that the community started building.”

**Stephane asks: Jonathan, can you talk about erasure.world: where we’re going to take it and how we’re going to display other projects that the community builds?**

Jonathan said that at the moment, Numerai has built most of the projects on top of the Erasure protocol: “we made it and we want to show people what MVPs and products look like on top of the protocol”. As people build new projects and products, Jonathan said that their plan is to display them on the [Erasure homepage](http://erasure.world) to show what people have been up to and include metrics around development activity.

If you have great ideas, share them in the [Erasure Community Chat](https://go.rocket.chat/invite?host=community.numer.ai&path=invite%2F9L7egf) or on Twitter by tagging [@ErasureBay](https://twitter.com/ErasureBay). Or you could be really cool and request the feature on [erasurebay.org](https://erasurebay.org/).

Haven’t used Erasure Bay yet? Check out [this tutorial](https://app.gitbook.com/@numerai/s/erasure/erasurebay-docs/new-bay-user-walkthrough) to set up your accounts and start making requests.

Don’t want to miss the next Erasure Bay office hours? Follow [Numerai on Twitter](https://twitter.com/numerai) or join the discussion on their [Telegram channel](https://t.me/NMR_Official) or [RocketChat](https://community.numer.ai/home).

Make sure you sign up below to get the Erasure monthly updates delivered straight to your inbox.

