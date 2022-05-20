---
title: "Gasless Smart Contract Wallet"
date: 2022-05-20T16:09:52+05:30
draft: false
---

Most wallets are designed for DeFi. A wallet that works for your DApp, probably needs to be designed ground up. 

# Gasless
I think gaslessness is an under explored opportunity in web3 - a way to interact with onchain contracts without having to pay the gas. L2s like Optimism, Arbitrum, Polygon have low gas fees - why don't we just use a cheaper chain for on-chain transactions/interactions? If you think gaslessness is about gas prices, you're mistaken. It is a question of end user experience. If the user has to spend brain cycles looking at gas prices, however small they are, it is a poor user experience. 

# In browser wallet
Every DApp is likely to have it's own wallet that is specifically designed for the usecases in the said Dapp - atleast for the next few months/years. Dapps should create a new wallet under the hood - probably in-browser. Each of these wallets might have different levels of security depending on what's relevant to the Dapp. For example, a wallet that is designed for DeFi, likely needs high security - thereby asking the user to hit confirm each time there is an onchain transaction that could potentially be a financial transaction. 

But if your DApp's primary usecase is to store and read _information_, your DApp doesn't require the user to hit confirm for every on-chain transaction as long as the transaction is gasless (i.e the user doesn't have to pay for the gas).

# Progressive Security
A web browser wallet is obviously insecure. But a fair tradeoff given the wallet is likely to have zero funds and assets to start with.

Once there are assets, the user should be able to migrate to more secure forms of the wallet. This is when the user would decide to move to metamask or a gnosis. When you want to progress on security, you can make the modification to a deployed smart contract wallet. That way, irrespective of the changes you make to the security - whether you're using an inbrowser wallet or a hardware multisig wallet, you still own the same onchain smart contract wallet. Your identity doesn't change even if you start using a different externally owned account. 

# Questbook
Questbook is a decentralized software. All the data is on chain or on decentralized storage. We don't run our own centralized databases or servers. And the user doesn't have to pay gas to interact on chain, thanks to the gasless smart contract wallet. That way neither is their identity at risk, nor do they have to compromise on user experience. 