---
description: Release of version 2.2 to the Creditcoin network.
---

# Version 2.2 - 2022-06-02

**Please note:** This version utilizing the Substrate framework is still in beta.&#x20;

The following updates/fixes were released to the Creditcoin network:

* Improved integration testing for an entire loan cycle, register address and updated testing to use creditcoin-js; Moved to the Creditcoin repo.
* Within the Creditcoin command family, we added timestamps when funding a DealOrder, and removed excess data from events.
* Created error message for when transfer verification fails, and initiated a retry transfer with verification.&#x20;
* Within CI, automated a check to bump versioning for runtime changes or modifications to extrinsics, and executed both on dev and testnet networks.  Established check to overwrite pallet weights before a release.
