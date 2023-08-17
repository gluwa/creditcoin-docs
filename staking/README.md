# Staking

## Proof-of-Stake (PoS) <a href="#proof-of-stake-pos" id="proof-of-stake-pos"></a>

Distributed ledger technologies use consensus mechanisms to agree on the validity of transactions and maintain a consistent and immutable record of the chain. In decentralized blockchains, this typically involves using various consensus algorithms, such as proof-of-work or proof-of-stake, to ensure agreement and prevent double-spending or malicious activity.

Consensus consists of two stages:

* Block production: how new blocks are created;
* Block finality: how one of the many block candidates is selected and added to the canonical chain.

Proof of Stake (PoS) is a consensus algorithm used in blockchain networks where validators are chosen to create new blocks based on their ownership or "stake" in the cryptocurrency. Validators are incentivized to behave honestly as they risk losing their stake if they attempt to validate fraudulent transactions, ensuring the security and integrity of the network.

## **Differences with Proof-of-Work (PoW)**

While PoW requires computational work and miners to compete against each other, which consumes significant computational resources and wasted energy, PoS relies on validators' ownership or stake in the cryptocurrency to create new blocks and secure the network.

Whilst PoW requires significant upfront investment in specialized hardware and energy costs, PoS mechanisms also require validators to “have skin in the game” in the form of staked cryptocurrency. Validators in PoS have a financial stake or investment in the cryptocurrency they hold. They are required to lock up a certain amount of their own cryptocurrency as collateral to participate in the consensus process. This collateral, known as a “stake”, serves as a form of guarantee, as validators risk losing their stake if they act dishonestly or validate fraudulent transactions. This economic incentive encourages validators to behave honestly and maintain the security and integrity of the network, as they have something tangible to lose.

## Nominated Proof-of-Stake <a href="#nominated-proof-of-stake" id="nominated-proof-of-stake"></a>

Creditcoin's Nominated Proof of Stake (NPoS) is a variation of the Proof of Stake (PoS) consensus algorithm. NPoS introduces a nominator-validator model where nominators can select and back validators. Nominators delegate their stake to validators, and in return, they can receive a portion of the validator's rewards. This system allows token holders, who may not have enough stake or technical expertise to become a validator, to nonetheless participate in the network and earn rewards by supporting trusted validators instead. Thereby, it promotes a more inclusive and secure network, as the nomination process enables a broader set of token holders to participate in consensus and governance than under a traditional PoS model.

## Validators <a href="#validators" id="validators"></a>

Validators participate in consensus by creating new blocks and finalizing previous ones. To be part of the active validator set, validator candidates must have a sufficient amount of stake behind them. Currently, the minimum required is 1000 CTC. This stake can be provided by a validator themselves, or from third-parties who support them, which we call nominators. All elected validators have equal block production rights, regardless of the amount of stake supporting them. This helps to ensure decentralization and security by preventing the concentration of staking power into a small group of validators.

## Nominators <a href="#nominators" id="nominators"></a>

Nominators can participate in NPoS consensus, without running their own nodes, by backing validators with their own stake, sharing both rewards and slashing (burning of stake for dishonest behavior) with any elected validators they have backed.
