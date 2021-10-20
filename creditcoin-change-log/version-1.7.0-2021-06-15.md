---
description: Updates - Improvements related to Hyperledger Sawtooth 1.0.5
---

# Version 1.7.0 - 2021-06-15

* Improved numerous performance and resilience issues for the REST API, processor and validator.
* Resolved issues on block reward allocation for miners.
* Introduced injection of housekeeping transactions improving decentralization of the network.
* Optimized code for retrieving state data from Sawtooth REST API.
* Resolved issues with fork resolution.
* Removed dependency on Sawtooth REST API from Creditcoin Processor.
* Resolved several race conditions which caused platform instability.
* Refactored peering and gossip code to improve performance and reliability.
* Implemented upgrade to validators: dropping stale connections and reacquiring valid peers.
