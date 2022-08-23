---
title: "Launching Questbook v2 open beta"
date: 2022-08-23T19:25:41+05:30
draft: true
---

Questbook's v2.0.1 doesn't only provide a great user experience for foundations to run their grant program and developers to apply to them - it sets a new all time high bar for web3 dapp UX. 

# Context
Foundations and DAOs grow the ecosystems via grants, bounties, partnerships, BD etc. These utilize funds from the _community_ allocation, aka the treasury. With Questbook, these processes can be run on-chain - giving complete transparency and accountability to the community on where and why funds are being deployed.  

If you've used our tool before, you'd know that every interaction on the product is an [onchain interaction](https://blog.questbook.xyz/posts/attract-builders-using-questbook/). Though this provided much more data transparency, it was a major step down in user experience. The user experience was definitively worse than using a Google Form.

But, not any more. 

This release marries the great user experience of Web2 and the onchain transparency of Web3. 

# Release Notes
As of today, the new experience is available on [gasless.questbook.app](https://gasless.questbook.app)
## App Specific Wallet - Zero Wallet
Embedded in Questbook's latest release is an inbrowser app-specific wallet, called the Zero Wallet. This Zero Wallet, gives users a zero click login into Questbook. Also, this wallet is not responsible for any financial transactions. The wallet balance of the Zero Wallet is always zero.

Users can now all of the following on chain, without paying gas!
- Setup new DAOs
- Create grants, bounties, job openings etc
- Review and evaluate applications
- Invite team members to the DAO
- Pay out the applicants

Users don't need to install a browser wallet extension, don't need to know "which chain", don't need to pay gas - and still have all of their interactions recorded onchain, and be transparent to the community on how treasury capital is being deployed. 

The best part? This works _perfectly_ fine on a mobile browser too! 
It's magical. It's unbelievable that this experience is even possible inspite of having onchain transactions.

We're delighted to partner with Biconomy to enable this experience for our users. 
Under the hood, data is being recorded on various chains
- Polygon
- Optimism
- Gnosis
- Celo
- Solana (via NEON)
- Many more coming soon!

But, as you'd have guesses, the user never has to "switch network". Infact, the user needn't even ever bother about the question which chain is this dapp functioning on.

You should try it out. 

## Safe integrations
If you've used the product before, you'd know that the way to send funds to users has been to use Questbook's own implementation of the multi-sig-safe. We've gotten rid of this constraint. 

We now know how hard it is to create a safe that's both flexible and secure. We've recently announced our investment in [Gnosis Safe](https://twitter.com/madhavanmalolan/status/1546882484146540545). We now integrate with safes. 

We not only support Gnosis Safe, but also all possible Safes across all chains. 
Our major customers want to disburse money from the multisigs their foundation runs on, so as of today we're launching 
- Gnosis Safe (on Polygon, Gnosis, Optimism, Mainnet)
- SPL Governance multisig Realms (on Solana)
- Celo Safe (on Celo)
- ... with a permissionless way to add more multisigs!

With this update, we're not only able to support various safes, but we can now utilize the rich feature space they offer. We're no longer constrained by the functionality of the Questbook multi sig. 

Most prominently, batching transactions. Users can now send funds from their multisig to multiple builders at once using batched multisig transactions. 

It's a major boost in convenience, especially if there are a large number of applicants to a grant program.

We're humbled to be building on the shoulders of giants like Gnosis, SPL Governance etc. It's a testament to permissionless, trustless composability.

## Graphs and reports
The major goal of running a grant program on Questbook and on chain, is that the program can be accountable to their respective communities. 

Though all the data has been stored onchain or on decentralized storage (IPFS), the data wasn't readily accessible for analysis. 

With this release, users can share their dashboard with the community and share information on important data points like
- How much money has been deployed
- How many applications came in
- How many applications were reviewed
- What was the turn around time
- ...

And, as you'd expect, these data points are also completely customizable. Users can choose what graphs are relevant for their audience and customize (with a little code) what data should show up on their dashboards. 

## Invite members to the DAO with onchain invite links
Previously on Questbook, if you wanted to invite a user to your DAO, you'd need to whitelist their wallet address and ask them to login with that particular address. Yuck. 

You can now create an invite link. The user just needs to tap on the link and accept an invite to the DAO. We're all used to this experience in Web2. But, it's not a trivial feat. This is a huge engineering win, because this invitation link is completely decentralized without storing a secret on databases as one would in a web2 product. 

If everything is to happen decentralized, on chain - it introduces a new attack vector of getting frontrun. If the invited user accepts an invite link by creating a transaction on chain, anyone else could look at that transaction in the mempool and frontrun the transaction, thereby getting themselves invited to the said DAO. 

But not with this web3 native invite links which [we've written about before](https://blog.questbook.xyz/posts/questbook-invite-links/). 

## Ofcourse, there's more
Above mentioned are the major changes that have gone in into this release. However, I do feel bad for a bunch of great fixes that have gone in that didn't make it to this list. 
But here are some other fixes
- A much simplified onboarding experience
- Simpler navigation across the product
- Landing pages for DAOs 
- Sorting and filtering of DAOs on the home page

... damn, there are still a few smaller fixes that I don't have patience to list any more. 

# Know someone who's running a grant program?
If you or someone you know is running a grant program for their foundation or DAO, we'd love to onboard them directly into v2.0.1!

{{<typeform id="SCB3gvID">}}




