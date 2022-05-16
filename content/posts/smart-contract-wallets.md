---
title: "Smart Contract Wallets v/s Metamask?"
date: 2022-05-16T13:35:07+05:30
draft: false
---
```
Can you explain from a user experience standpoint how a smart contract wallet is different & better from metamask?
```

Smart contract wallets are not a replacement of Metamask.
The fundamental to understand here is that in ethereum and crypto, code is a first class citizen. You can write code that acts and behaves on behalf of a user. In contrast, this is not the case in web2 where humans are first class citizens and code is always blocked away with tps throttling, captchas etc.
In web3 there are two types of accounts - user accounts (called externally owned accounts) and contract accounts. If someone is writing a dapp, it is impossible to distinguish between the two. Has the dapp smart contract been invoked from a user account or a contract account - no way to tell.
That made smart contract wallets possible. What they said was, I'll deploy a smart contract and the user can interact with other apps via this smart contract. The keyword being via.

The contract account has an address just like your metamask. When you say mint an nft via this smart contract wallet, the nft is minted to the address of the contract account (not user account).
You still need to interact with the smart contract wallet using a user account. So the data flow looks like user account -> smart contract wallet -> dapp. But if you were using metamask and no smart contract wallet, it would have been user account -> dapp.

So, you need metamask still to interact with your smart contract wallet and the smart contract wallet will interact with the dapp on behalf of your metamask or user account.

Huh. That doesn't make any sense. Why are we adding a step in between?

There are 3 things that matter imo, which is not possible without introducing the step in between.
1. Gasless : if you want to enable gasless interaction without changing the existing code or you want to enable gasless on deployed dapps, you need have metamask sign some data => send to a relayer => send to smart contract wallet => interact with dapp. What happens if the smart contract wallet doesn't exist? You can still do a gasless transaction metamask->relayer->dapp. But, if say you are minting an nft, the nft will be minted into the account of the relayer to which you have no control. But if it goes via the smart contract wallet, the nft will be minted to your smart contract wallet, which you do have control of.
2. Security: you can have different modes of security. See also my article on [progressive Security in wallets](https://mirror.xyz/madhavanmalolan.eth/Zfx_YgU2VZ4doh6S3i9wngf5OaTAfTiv-FguoGxeWF8). You can say stuff like interact with this dapp only if 3/5 signers approve. A multisig is a smart contract wallet. You can replace the signer - if your metamask is compromised, you can update the signer on the smart contract wallet and continue business as usual. But, if you didn't have the smart contract wallet and we're using metamask and your metamask private key got compromised - there is no way to secure your funds other than transferring all erc20 tokens, all NFTs etc into a new account. In some [dapps like ours](https://questbook.xyz), there are things that can't be transferred eg. who is the admin of the workspace. What if the dapp doesn't have a way to update the admin so that you can set the new metamask wallet address as the admin? But if it was a smart contract wallet, the dapp always interacts only with the same address of the smart contract wallet, and the smart contract wallet has mechanisms to update which metamask wallet is authorised to go via this smart contract
3. Social recovery : this is similar to the above, in that scw are more secure. Now let's say you lost access to your private key. But you had a smart contract wallet that had 5 signers. If 3/5 signers approve, you can change the metamask address that can go via the smart contract. So automatically, the previous compromised wallet is rendered useless in who so evers hand it is in, and your new metamask wallet can operate the smart contract wallet as of nothing at all happened.

