---
title: "Gasless Smart Contract Wallet Implementation"
date: 2022-05-25T16:33:15+05:30
draft: false
---
This implementation borrows from EIP 1776 and EIP 4337. However simplified for a the use case of letting a dapp onbard a user to their platform without having to pay for the gas or install a wallet. 

# Assumptions
- The Dapp that wants to subsidize the gas for the user is a central entity, ie. the relayer. We're not decentralizing the relayer network as proposed in [EIP 1613](https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1613.md)

# User identification - OAuth
A centralized relayer can subsidize the gas of the end user. However, the centralized relayer may have it's own way to identify the user. This could be by asking the user to login using an Oauth.

All the transactions on chain transactions that will be executed by the user will be sent via the relayer. The frontend will also attach an access token.

```
  axios.post(`https://relayer-url.com/relay`, { transactionData, accessToken });
```
The `/relay` endpoint may have custom logic to determine whether or not it wants to subsidise the said users' gas.


# Burnable wallet
When the user opens the app for the first time and provides OAuth access to the dapp, the user will be able to generate a wallet in browser. This will create a private key and store it in local storage.
```
localStorage.set('pvtKey', web3.eth.accounts.create())
```

# Smart Contract Wallet
Right after the burnable wallet is created, a smart contract wallet is deployed.
The default signatory of the smart contract wallet is the above created burnable wallet.

```
  axios.post('https://relayer-url.com/new_wallet', { address, accessToken });
```

This smart contract wallet allows for
- Upgrading security, from burnable wallet to something more secure like browser wallet, hardware wallet, multisig.
- Social recovery inbuilt even if user loses access to their signatory wallet, they can recover the wallet and just change the signatory
```
contract SmartContractWallet {
  address signatory;
  constructor(address _signatory){
    //...
  }

  function call(bytes calldata, bytes metaTxSignature) {
    require(isAllowed(calldata, metaTxSignature), "Only signatory can use this wallet");
    call(calldata);
  }
  
  function call(bytes calldata) internal {
    //...
  }
  function changeSignatory(address newSignatory, bytes metaTxSignature) {
    require(isAllowed(bytes(newSignatory), metaTxSignature));
    //...
  }
  function addSocialRecoverer(address recoverer, bytes metaTxSignature) {
    //...
  }

  function recover(address newSignatory) {
    //...
    // if k/n recoverer call this function with the same newSignatory, change signatory
  }
}
```

# Relayer
The relayer must take the `transactionData` on its `/relay` endpoint and execute the transaction onchain via the smart contract wallet.
```
  getSmartContractWallet(address).call(calldata, signature);
```
It is completely upto the relayer to subsidise the gas or not. It can chose to reject relaying

# Censorship protection
The relayer architecture is just an optimization. Because the gas is subsidised and the transaction with external contracts happen via the smart contract wallet, the user may call the smart contract wallet's `call` function without the relayer and pay the gas from an EOA. That way, the relayer cannot stop any user from executing some transaction - it can only make it a little bit frustrating. 

# Universal
This smart contract wallet can then be used to interact with any external smart contract. The external smart contracts need no change at all. 

So that way, this smart contract wallet can become a user's primary smart contract wallet. All their credentials and soulbound NFTs that are rewarded to this address, can be used across the board. 

I think this is going to be huge. Every user has a smart contract wallet. So their address on chain remains unaffected even when their primary wallet's private key is compromised. 
