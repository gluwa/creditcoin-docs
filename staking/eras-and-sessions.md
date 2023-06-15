# Eras and Sessions

In Creditcoin's Nominated Proof-of-Stake blockchain, time is organized using three distinct units: blocks, sessions and eras.

Validator elections are run at the end of each **era**. An era is a period of **24 hours** during which an **active set** of validators is producing blocks and performing other actions on the chain. Not all validators are in the active set and such set changes between eras.

Each era is divided into two **12 hour sessions**, during which validators are assigned as block producers to specific time frames or **slots**. This means that validators know the slots when they will be required to produce a block within a specific session, but they do not know all the slots within a specific era. Having sessions adds a layer of security because it decreases the chance of having multiple validators assigned to a slot colluding to harm the network.

Ideally each slot should produce one **block** every **15 seconds**. A block is the smallest time unit in the Creditcoin blockchain.

| **Unit** | **Time**               | **Reward** |
| -------- | ---------------------- | ---------- |
| Block    | 15 seconds             | 2 CTC      |
| Session  | 12 hours (2880 blocks) | 5760 CTC   |
| Era      | 24 hours (2 sessions)  | 11520 CTC  |
