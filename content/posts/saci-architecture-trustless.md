---
title: "Questbook uses a trustless software architecture"
date: 2022-06-05T16:57:54+05:30
draft: false
---

Questbook can never shutdown, even if the founders want it to.
Questbook implements a completely decentralized software architecture called [SACI Software Architecture](https://mirror.xyz/madhavanmalolan.eth/0h9QKmgfPFqlaU1nwr-llRuIwKxhTXPt9ar0TDKZLCU)


# [S] Storage is decentralized
This means that all the data of using the Questbook dApp is either on chain or on decentralized storage like IPFS and Filecoin.

We don't control your data. You are in control of the data, using your keys. All the data that is private is encrypted using the public keys of the users who are allowed to access the data. 

The data is public. The private information is encrypted. All of this is stored on decentralized storage. The blockchain is our database.

# [A] App is serverless
We don't run our own servers or database. The app itself is a react-app that is served via IPFS. Even if we shut down Questbook, the app will continue to be served by IPFS nodes. Since all the logic is on chain too, all the app will be fully functional with or without Questbook's involvement. 

Questbook is involved only to the extent to keep improving the product and experience. 

# [C] Contracts are all on chain
Creating a program, accepting applications, evaluating milestones and disbursing capital all happens on chain. That way, you never need to worry about malicious activities on the part of Questbook - because all the [business logic is agreed upon](https://blog.questbook.xyz/posts/work-improvement-proposals/) and implemented in open source verifiable code. 

All the functionality of Questbook can be leveraged without using the Questbook App. You can create your own app/frontend to interact with the on-chain contracts to get the exact same result. Trust the contracts, not us.

# [I] Indexers serve data
All the data is delivered to the front-end not using any centralized server. All the data that is made available to the dApp is using decentralized indexers that are indexing onchain events and transactions. Every operation is an onchain transaction and served to th UI using trustless indexers like The Graph Protocol. 

# Trust the code, not Questbook.
You never have to worry about us misusing your data because we, really, can't.
