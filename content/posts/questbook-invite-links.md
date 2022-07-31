---
title: "Questbook Invite Links: The web3 OTP"
date: 2022-07-30T18:00:10+05:30
draft: false
---

## The Problem

Web3 is a nascent stack, and a major challenge dApps like QuestBook face is educating users about web3 terminology and delivering products that are easy to use products as well as decentralised.

One of QuestBook's workflows allowed DAOs to invite their team members to their organisation on QuestBook. However, to add the user to their organisation on chain, the organisation owner had to ask their team for their respective wallet addresses -- which can feel unnatural, since wallet addresses have no easy-to-remember pattern like email addresses do. 

We received a lot of feedback on the above mentioned flow from DAOs asking if there's a way for them to add their members via email or generate an invite link to send their team. Realising this is a UX problem we need to resolve for our users, we got to work.

## Coming Up With a Solution

To allow users to invite by email, we'd need to verify that the wallet wanting to join the organisation actually owned the email address that was invited. This entire flow had be on-chain and we couldn't think of a sane way to accomplish verifying the email on chain. So, we decided to tackle the invite link flow. Could we generate an invite link that an organisation owner can share with their team member, which they can use to join the organisation? And can we accomplish this purely on-chain?

We believed we could make it work somehow, and so we came up with a few approaches.

The inviter could hash a secret and then include the secret in the invite link and send this across to the invitee. The invitee would then pass the secret to the smart contract, which could then hash and check if the secret matched, if it does -- we accept the invite and the user joins the DAO. Voila, on chain invites.

The problem with the above approach was that it could be front run, anybody observing the transaction could pay more gas and wrongly get into the organisation.

## The Solution

To resolve this front running problem, we thought of using public/private key crypto and so, we came up with the following framework -- labelling it "Anon Authoriser":

1. Let's assume Alice wants to authorise Bob to take a certain action. In this case, Alice is the authoriser.
2. Alice Creates a public-private key pair `(Pu, Pr)` & compute address `A = Address(Pu)`.
	- Note: your ETH address is a function of your public key -- which is `A` in this case
3. She denotes the purpose of the authorisation with a flag F. This flag prevents Bob from using Alice's authorisation to undertake another action that she hasn't authorised
	- In our invite link case, the flag can be the hash of the organisation and role the invited user would undertake. This prevents misuse of the same invite.
4. She then asks the SC (smart contract) to store this as a pending authorisation with the call: `generateAnonAuthorisation(A, F)`
5. SC stores Alices wallet `Wa` and flag F against the address A
6. SC ensures this address hasn't been used already & returns successfully
7. Alice sends Bob her wallet address, the private key and authorisation flag (Wa, Pr, F)
8. Bob signs his wallet address (`Wb`) using `Pr` `S = Sign(Wb, Pr)`
9. Bob requests the SC to verify authorisation using `anonAuthorise(Wa, F, S)`
10. Solidity signature check returns the address that signed the message. The SC uses this to verify the signature sent by Bob, the message being Bob's wallet address `A' = Verify(Wb, S)`
11. SC checks if there is a record stored against `A'`
12. Finally, SC checks that the authoriser specified (`Wa` in this case)
and the flag of purpose F specified match the existing record.
13. If everything matches, SC returns successfully and deletes the record
so it cannot be used again
14. Bob is now considered authorised. 
	- `Pr` can even be published online as it cannot be used now
15. Note: this entire approach cannot be front run because in order to do that, another user would need to sign their wallet address -- for which they'd need the private key, and that they don't have access to.

![Anon Authoriser Flow](../images/anon_authoriser_flow.png)

## The Labour

Once we had a framework in mind, we had to prove this works & so we built out this approach in a solidity smart contract, which you can access [here](https://github.com/questbook/anon-authoriser). This repo contains the SC & JS utils required to utilise anon-authoriser.

Then, we incorporated this flow into our grants smart contract to truly enable this invite link flow in our dApp. You can find the PR for the implementation [here](https://github.com/questbook/grants-contracts-upgradeable/pull/14)

Finally, the last leg of the solution was building out the frontend to interact with this SC, which you can find [here](https://github.com/questbook/grants-frontend/pull/420)

## The Fruit

Our theory worked, we now had a secure, fully decentralised way to generate invite links on chain. We built the web3 equivalent of an OTP. You can create a DAO on QuestBook and [try it out](https://www.beta.questbook.app/) now!

### Preview

What it looks like to create an anon-authoriser link

![Create Invite Link](../images/create_invite_link.png)
![Created Invite Link](../images/created_invite_link.png)

What it looks like to join an anon-authoriser link

![Join Invite Link](../images/join_invite_link.png)
![Joining Invite Link](../images/joining_invite_link.png)