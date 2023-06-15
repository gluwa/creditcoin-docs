---
description: Release of version 2.1 to the Creditcoin network.
---

# Version 2.1 - 2022-05-02

**Please note:** This version utilizing the Substrate framework is still in beta.&#x20;

The following updates/fixes were released to the Creditcoin network:

* Improved loan command structure for more seamless partner integration. Created more structure around interest rate declaration of type in terms (whether it is simple or compounding, rate per period, decimal declaration and period).  This also extended to a rework and improvement to Register Transfer.
* Improved security of Register Address by requiring “proof” of ownership via a signed message.
* Established check on nonce when verifying Ethless transfers, and updated error messaging accordingly.
* Improved fee structure to correlate with extrinsic weighting, runtime benchmarking and command structure.
* Per miner requests, we exposed metrics for monitoring hash rates, and established alerts to monitor RPC nodes.
