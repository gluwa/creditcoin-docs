---
description: >-
  The goal of Creditcoin 1.8 was to upgrade Hyperledger Sawtooth v1.2.6, and
  transition from Python to a Rust implementation.
---

# Version 1.8 - 2022-03-28

* Upgraded Hyperledger Sawtooth to version 1.2.6 (up from 1.0.5)
  * Attempts to improve the transaction processor and validation logic in efforts to curtail invalid transactions.
  * Added fixes toward networking improvements and gateway performance.
  * Attempts to improve stability and performance of the validators; Added functionality to consensus validation and node validator
  * Attempted to fix dynamic difficulty spikes and lagging difficulty that was occurring in an effort to improve block validation times.
* Reduced the size of Creditcoin snapshot - adding efficiencies allowing faster syncing, and quicker setup for miners.
* Added "Register Deal Order" command to the Creditcoin command family.
* Core journaling and database access were rewritten in Rust.

**The download links for the 1.8 snapshot are located here:**

Google Drive - [https://drive.google.com/file/d/1m9E0GXtS5Pbesn761Xl101qVDZ8e9zPK/view?usp=sharing](https://drive.google.com/file/d/1m9E0GXtS5Pbesn761Xl101qVDZ8e9zPK/view?usp=sharing)

**General advisory notes concerning the 1.8 version and release:**

* Old images cannot be stopped from joining the network and will continue to disturb the network.
* Peering issues remain with frequent, long forks occurring.
* Nothing stops nodes from starting a network from scratch and attempting to resolve their own chain from very low heights.
* Broken or faulty comms between validator/consensus can trigger unrecoverable errors in the consensus depending on the missing event/timeout or state in the publishing state machine.

**Public Notice: Creditcoin 1.8 (and all older versions) are now designated as "legacy" in all Creditcoin repositories on Github.  Because of the issues described above with v1.8, and the ongoing issues with supporting Hyperledger Sawtooth, the Creditcoin Foundation has made the decision to no longer support Hyperledger Sawtooth.  A Creditcoin version 2.0 version has now been released using the Substrate framework. Please see the Version 2.0 Change Log.**

**For more information about this transition to Substrate, please see our** [**Medium Post "Creditcoin 2.0"**](https://medium.com/creditcoin-foundation/creditcoin-2-0-d9bbca02991a)**.**
