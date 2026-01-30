---
description: Release of version 2.3 to the Creditcoin network.
---

# Version 2.3 - 2023-08-31

Version 2.3 of Creditcoin introduces some of our largest updates so far. Chief among these is the change from a SHA3-based Proof-of-Work consensus to a more accessible and environmentally friendly Nominated Proof-of-Stake (NPoS) system. The introduction of NPoS means community members will be able to participate in strengthening the network and receiving rewards without having to run and maintain their own Validator nodes. Validators additionally benefit by no longer need to invest in high-powered computers or the energy needed to run them. These changes help ensure the longevity and scalability of the Creditcoin blockchain for years to come.

We've also introduced several completely new components to the Creditcoin ecosystem. The [Creditcoin Staking Dashboard](https://cc-enterprise-staking.creditcoin.org/#/overview) provides a clean interface for users to monitor and manage their stake and their rewards. The [Creditcoin CLI ](https://github.com/gluwa/creditcoin/tree/dev/scripts/cc-cli)offers the more technically minded a simple way to perform common tasks when managing their Validator nodes and can be integrated more easily to create custom scripts and actions.

Below is a list of the most notable changes and additions.

#### Creditcoin Node

* Add BABE pallet for block slot assignment
* Add GRANDPA pallet for block finalization
* Add support for GRANDPA authorities past block #0
* Add registerAddressV2 extrinsic with support for additional signing methods
* Update runtimeUpgrade script to include rotateKeys function
* Update Testnet spec with grandpa Initial Authorities and add fallback
* Initialize BABE pallet on runtime upgrade
* Implement custom pallet for switching consensus mechanisms
* Add Creditcoin zombienet template for spawning/testing at scale
* Added an official Security Policy for reporting vulnerabilities and concerns
* Increase maximum active/waiting validators to 100,000
* Change the reward per block to 2 CTC
* Add handling to smoothly phase out PoW and related rewards
* Validate compatibility with previous APIs

#### Creditcoin-JS

* Add support for registerAddressV2 extrinsic
* Update types definitions
* Misc/security dependency updates
* Improve logging

#### CC-CLI (Initial Release)

* Support for the following commands:
  * `balance` Get the balance of an account
  * `bond` Bond CTC from a Stash account
  * `chill` Signal intention to stop validating from a Controller account
  * `distribute-rewards` Distribute all pending rewards for all validators
  * `new` Create a new seed phrase
  * `rotate-keys` Rotate session keys for a specified node
  * `send` Send CTC from an account
  * `set-keys` Set session keys for a Controller account
  * `show-address` Show account address
  * `status` Get staking status for an address
  * `unbond` Schedule a portion of the stash to be unlocked
  * `validate` Signal intention to validate from a Controller account
  * `withdraw-unbonded` Withdraw unbonded funds from a stash account
  * `wizard` Run the validator setup wizard. Only requires funded Stash and Controller accounts.
  * `help` Display help for a command.
* Support legacy ECDSA keys for signing

