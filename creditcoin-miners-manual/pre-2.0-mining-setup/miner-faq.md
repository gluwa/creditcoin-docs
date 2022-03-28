---
description: Frequently-Asked-Questions for the Creditcoin developer community.
---

# Miner FAQ

## I'm receiving the error "The validator has no genesis block, and is not yet ready to be queried." when trying to use the Creditcoin Client

This is often because your node has not yet downloaded the blockchain.

To speed up the process of obtaining the entire blockchain, we regularly provide snapshots of the Blockchain. See the _Download Snapshot_ section of the [Update Creditcoin Nodes](updating-creditcoin-nodes.md#04db) page for more information.

## Troubleshooting suggestions

1. Ensure that your \~/Server/gatewayConfig.json file contains `erc20` and `ethless` sections and they are filled in correctly (See [Creditcoin Miner's Manual](../#server-gatewayconfig-json))
2. Pull the latest version of the docker-compose files from [github.com/gluwa/CreditcoinDockerCompose-Mainnet.git](https://github.com/gluwa/CreditcoinDockerCompose-Mainnet.git)
3. Make sure you have the latest docker images (See [Updating Creditcoin Nodes](updating-creditcoin-nodes.md#e110))

## Join our Discord Community!

For a quicker response to your question - please [join our Discord community](https://discord.com/invite/creditcoin) and ask your questions directly to the Creditcoin Foundation!\


