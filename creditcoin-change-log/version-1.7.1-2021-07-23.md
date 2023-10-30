---
description: Updates - Improved Hyperledger Sawtooth 1.0.5 Stability issues
---

# Version 1.7.1 - 2021-07-23

* Excluded self-endpoint on ConnectionManager start.
* Increased depth\_limit in housekeeping-block-fetching request as much as possible.
* Fixed bug: Unhelpful error message could lead to user accidentally transferring crypto multiple times.
* Fixed bug: Batch failed signature validation.
* Quality of life improvements for Creditcoin Client.

To update, users should make sure they're referencing docker images with `1.7` tags:

```
gluwa/creditcoin-client:1.7
gluwa/creditcoin-validator:1.7
gluwa/creditcoin-processor:1.7
gluwa/creditcoin-validator:1.7
gluwa/sawtooth-rest-api:1.7
```

Then, `stop` their node,  `pull` the new images with `docker-compose -f Server/docker-compose.yaml pull` , and finally `up` their instance(s). Details are available [here](https://github.com/gluwa/creditcoin-docs/blob/642ab6da00b1e94e3f475bc7b30c6817593937cc/creditcoin-miners-manual/pre-2.0-mining-setup/updating-creditcoin-nodes.md)
