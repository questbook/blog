---
title: "Questbook Composability"
date: 2022-06-05T17:25:19+05:30
draft: false
---

Questbook is web3 dApp. That means it is naturally composable. 
Since Questbook doesn't run it's own centralized servers and databases, all the data is always publicly visibile and can be used by builders to build great new experiences. 

Here are a few ways you can compose on Questbook

# Open sourced repositories
You can contribute directly to our source code. 100% of our codebase is open sourced, and always will be. We don't have any company internal private repositories or CVS.

All the repositories can be found at : https://github.com/questbook

However, the ones you probably need to pay most attention to are : 
1. [Smart contracts](https://github.com/questbook/grants-contracts-upgradeable) : EVM Compatible Solidity Contracts deployed on multiple chains
2. [Frontend](https://github.com/questbook/grants-frontend) : React Application served via IPFS
3. [Indexer](https://github.com/questbook/subgraph) : The indexer that collates data for use by the frontend 

# Zapier
Every transaction that is exectuted and confirmed on the chain is emitted and indexed by the indexer. However, if you want to trigger some specific business logic to your program, you can do so by using the events and data that are pushed to Zapier using [this Zap](#coming-soon)

# On chain data analysis
All the contracts emit data and information onchain. 
You can 
- Request for more data to be emitted by submitting a PR to the open sourced library of smart contracts
- Build your own data visualization using your own tool or thirdparty tools like Dune Analytics
