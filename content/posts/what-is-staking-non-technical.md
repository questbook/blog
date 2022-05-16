---
title: "What Is Staking Non Technical"
date: 2022-05-16T14:16:54+05:30
draft: true
---
```
Can you explain the economics behind the concept of staking from a non technical point of view?
```

Sure. Different staking mechanisms have different mechanisms but they do have some similarities which I'll touch upon.
The basis behind the blockchain as in bitcoin was that you secure the blocks by computing a certain number every 10 mins (called nonce). That is 10 min of high intensity computation. The security assumption is that if you are spending $100 of electricity in doing the computation, and getting rewarded something that is worth $101, it's profitable to do those computation aka mining.
The movement of proof of stake started in 2013-14 with a project called Casper. The premise was that the 10min of computation done was actually wasteful ; the only thing that matters is finding the nonce. Once the nonce is found you can practically throw away all the other computation you had done.
At this point, bitcoin was dominated by Asics. Asics were computers that could do nothing else but mine bitcoin. So the game became how powerful an asic you could buy. If you have spent $1M in buying an asic but doing something malicious, other nodes won't anyway agree on what you mined and you will lose all the money that you spent in form of electricity bills.
What pos did was model the same dynamics without doing the wasteful computation bit.
Buy asic = put a stake
Lose electricity bill = stake slashed // when malicious behaviour
Block rewards are the same in both cases
Proof of stake argues that pos is more secure because of how much you can slash if someone misbehaves. In pow you lose only 10min electricity bill, but in pos you can potentially lose all of your stake ($1M) if you misbehave.
So in pos basically what you're saying is i am willing to lose $X if i misbehave. That X determines how much security you're adding to the system. But if you behave correctly, you get block rewards in the chains native token. Many times called the yield in pos, block rewards in pow.
