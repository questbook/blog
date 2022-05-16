---
title: "What Is Questbook"
date: 2022-05-16T14:57:00+05:30
draft: true
---
Questbook is in the business of increasing economic mobility of builders. 
We're innovating on the future of work on multiple dimensions. Here, I'll outline the various things that we're launching in Q3 2022.

# Permissionless work
An Uber driver can get work on tap of a button, but the best of the best developers cannot get work on tap of a button. How do we fix that?
In enabling this future, we first need a marketplace of capital for building and builders - for seamless matching to be possible.

# Grants - a web3 native incentive model
Protocols, projects and DAOs have abundance of capital in their treasury. Many times in their native crypto-currency. They typically setup a grant program to deploy money from this treasury. The job of the treasurer is to deploy the capital in such a way that the money that remains in the treasury increases in value. Builders who add value to the project by composing on top of their protocol - increase the value of the underlying protocol. For example, Uniswap almost single handedly added all the DeFi value to Ethereum, making Ethereum itself more valuable. Now dapps built on top of Uniswap, make Uniswap more valuable - reflected in the price of $UNI. Uniswap treasury is now worth $15B. This money has to be deployed to make Uniswap and $UNI even more valuable. 

[Questbook Grants Tool](https://questbook.app) helps protocols run their entire grants program completely on chain, and builders can come and discover various grants programs and choose the project they compose on top of. 

# On chain grants
Having the entire grants program on chain enables the following. 
## Complete transparency
There are various stages in a grant program.
1. A grant program is created, and funded. Money is earmarked to be distributed to developers. We keep hearing about billion dollar plus grant programs, but most of those claims are just verbal. Having the commitment on chain transparently makes the developers trust that the money actually exists to be disbursed.
2. Applying for a grant. Once the grant is created developers can apply for grants and designate milestones that they will be hitting enroute claiming the grant. 
3. Updating milestones. Grant review committee reviews grants when milestones are hit and disburses part of the grant amount. Each time a milestone is hit, the builders credibility is built on-chain. These milestones are reviewed by the grant committee using rubrics, and the feedback is transparently shared with the applicant
4. Payout happens. When all the milestones have been hit, the project gets the whole grant amount. This transaction onchain gives confidence to future builders that if they complete the milestones, the payouts actually happen on time. 

## Builds credentials
Since everything is on chain, all the actions of the grant committee and the builders is recorded on chain. So, their behaviour is permanently visible. Giving a strong incentive for the grant committee to be transparent and fast in their reviews, and an incentive for builders to not cheat the grant committee. This credential can be a valuable input into various other parts of the ecosystem. 

# Shortcomings we've fixed
## Great user experience with custom wallet
If everything is on chain, it means that the users will have to install a wallet extension, hit confirm each time they have to make an update in the application process. Sucks. All wallets are designed for DeFi or NFTs. Most of the "onchain transactions" aren't financial in nature. Meaning, they don't need the level of _security_ that mandates a tap on confirm each time some action is being taken. Our transactions are data transactions, not financial transactions. We have built an in-browser wallet accompanied by a smart contract wallet. This allows us to not have to tap confirm for every data transaction. And ofcourse, we enable gasless transactions. So the end user doesn't have to pay gas - again removing the need to tap confirm. Using our dual wallet architecture we're able to mimick a web2-esque experience, and yet having all the data on-chain.

## Delegated grant allocators 
There is no way a single grant allocator can do a good job disbursing $200M. The allocator needs to be closer to their target audience. Builders won't come to grant allocators, the grant allocators have to go where builders are. Questbook allows running a distributed grants program. 
Each sub domain in the grant program, e.g. geography specific, theme specific (DeFi, NFT, P2E ...), can and should have a separate grant allocator. 

### Community run grant programs
Historically, the way to involve the community in running any form of governance, grant programs including, was to have a vote on each proposal made. That is [super inefficient](https://vitalik.ca/general/2021/08/16/voting3.html).
On Questbook and the grants protocol, we expect the delegated allocator to have a final say in every decision - to optimize for efficiency and speed of the capital allocation. The allocator may have a team of their own, but it is completely their decision. 

The community has only one power, a very important one. To replace the capital allocator. If there is a capital allocator that the foundation decided to run grants in India. But what if the community doesn't trust this grant allocator. The community can start a no-confidence motion. They can all participate in voting to replace the capital allocator. Who gets to participate in the voting and [how to cast votes](https://blog.ethereum.org/2014/08/21/introduction-futarchy/) shall be discussed in a post of its own. 

## Credentials
As and when the grant programs progress, the credentials accumulate. Builders now have a track record that can be queried. But also, additional signals from the builders' onchain activity and offchain credentials can be used to gate who gets to participate in various steps of the workflow. These credentials will also be made accessible to other dapps to build on top via APIs and libraries. This is an active area of research internally - and we have had major breakthroughs - which will be documented in a separate whitepaper.

# Buidl Protocol
All of the above innovation will directly impact builders' access to capital by means of grants. But that's where the story starts. 
We're also launching a Buidl Protocol that encapsulates all the stages of a builder - from building prototypes, getting access to grants, launching the product, getting access to follow-on capital. 
Questbook will become the home to the best innovations happening in the space - by making sure the best projects always have access to capital to push the boundaries of web3. 




