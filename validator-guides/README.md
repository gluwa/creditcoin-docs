# Validator Guides

## Tasks and Responsibilities <a href="#tasks-and-responsibilities" id="tasks-and-responsibilities"></a>

Validators are critical to maintaining the network. They maintain the Creditcoin network by producing and finalizing blocks through the Nominated Proof-of-Stake system. Validators in the active set have a responsibility to be online and execute their tasks. When performing validation tasks, they are accountable not only for their own stake but also the stake of the nominators that back them.

Node Operators have two main responsibilities:

* Keeping their validator nodes highly available
* Protecting their signing keys to prevent attackers from taking control and performing malicious actions using the validators identity.

Currently, operators run validator nodes and manage session keys, produce new block candidates in BABE, vote and come to consensus in GRANDPA, and, possibly, hold certain other responsibilities regarding data availability and XCM.

## Rewards and Slashing <a href="#rewards-and-slashing" id="rewards-and-slashing"></a>

Validators get rewarded at the end of each era according to how many era points they have collected. These points are earned by producing blocks. When an era ends, rewards are distributed between validators and their nominators according to their relative stake and the validator's commission parameters.

Validators have the ability to configure and receive a commission, allowing them to earn a percentage of nominator block rewards based on their chosen parameters. Validators can only set a percentage-based commission, rather than a figure-based commission. 0% commission means that the validator does not receive any proportion of the rewards besides that owed to it from self-stake, and 100% commission means that the validator operator gets all rewards and gives none to its nominators.

## Transitioning from Mining <a href="#transitioning-from-mining" id="transitioning-from-mining"></a>

Creditcoin 2.5 replaces Proof-of-Work mining with Nominated Proof-of-Stake voting. Operators who used to maintain the Creditcoin network and get CTC rewards will have to convert from miners to validators as explained in this guide. In order to continue participating in block production and consensus, they can either run their own validators by staking their CTC and getting backed by other community members, or participate as nominators by staking their earned CTC without having to run their own nodes.
