# Staking Rewards

Validators who produce a block are rewarded with tokens, and they can share these rewards with nominators backing them. Both validators and nominators can stake their tokens on chain and receive staking rewards at the end of each era. The staking system pays out rewards equally to all validators regardless of the total stake backing them. Thus, having more stake in a validator does not influence the amount of block rewards it receives. This avoids the centralization of power to a few validators.

There is a probabilistic component in the distribution of rewards, so they may not be exactly equal for all validators. In fact, during each era validators can earn era points by doing different tasks on chain. The more the points, the higher the reward for a specific era. This promotes validators' activity on chain.

## Validator Payouts <a href="#validator-payouts" id="validator-payouts"></a>

Validators and Nominators are rewarded at the end of each Era according to their earned Era Points. Points are obtained by validators who produce blocks during their designated time. Blocks which end up being finalized and added to the canonical chain score 20 era points. The Creditcoin network also distributes minor rewards to validators who produce uncle blocks, which end up not being included in the canonical chain, and authors that reference previously unreferenced uncle blocks.

> ![:info:](https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/atlassian/info\_32.png) An uncle block is a block that is valid in every regard, but which failed to become canonical. This can happen when two or more validators are block producers in a single slot, and the block produced by one validator reaches the next block producer before the others. We call the lagging blocks uncle blocks.

| **Task**                  | **Reward**    |
| ------------------------- | ------------- |
| Produce non-uncle block   | 20 era points |
| Reference new uncle block | 2 era points  |
| Produce uncle block       | 1 era points  |

The Creditcoin blockchain rewards non-uncle block producers with 2 CTC per block. With block time set at 15 seconds, each Era generates and distributes 11520 CTC.

### **Splitting Rewards among Validators**

Assuming all validators are honest and always online when required, block production slots for an era are distributed evenly among them, no matter their total stake. Creditcoin's implementation uses BABE block authoring to blindly assign these slots in a secure way. Ideally, they should all earn a similar amount of era points and thus a similar amount of tokens.

Total stake behind each validator does not affect reward distribution. Assuming there are only 4 active validators in an era, if every validator is online when required, when the era ends each of them should get 2880 CTC (1/4 of the total era reward).

* Validator #1 with 1M CTC stake: 2880 CTC reward
* Validator #2 with 500.000 CTC stake: 2880 CTC reward
* Validator #3 with 25.000 CTC stake: 2880 CTC reward
* Validator #4 with 100 CTC stake: 2880 CTC reward

### **Splitting Rewards among Nominators**

Once a validator is rewarded CTC, the newly minted tokens are distributed among all of its backers (both the nominators who voted for them, and the validator themselves). Validators can and are encouraged to stake themselves. Rewards are distributed to nominators and validators based on their relative stake amount. Validators are also able to retain a pre-defined percentage of nominator rewards as a commission fee.

Example: A Validator is rewarded 4000 CTC for its contributions to block production. This validator is backed by 1000 CTC staked by four different users:

* Validator's self-stake: 200 CTC
* Nominator #1: 400 CTC
* Nominator #2: 300 CTC
* Nominator #3: 100 CTC

The validator has set up a 1% commission that is calculated before distributing rewards. After the validator fee, there are 3960 CTC to be distributed among the four accounts.

* Validator payout: 40 CTC (commission) + 200/1000 \* 3960 = 40 + 792 = 832 CTC
* Nominator #1 payout: 400/1000 \* 3960 = 1584 CTC
* Nominator #2 payout: 300/1000 \* 3960 = 1188 CTC
* Nominator #3 payout: 100/1000 \* 3960 = 396 CTC
