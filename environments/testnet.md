# Testnet

Creditcoin Testnet usually runs newer versions of the Creditcoin runtime which are under active development and testing. It is the recommended network to try out new features.

## Proof-of-Stake Testnet

Currently, Creditcoin's Testnet is running a new consensus mechanism based on Nominated Proof-of-Stake. Users are encouraged to try out the new features and collaborate on testing the new Validator and Nominator roles. Find out more about Proof-of-Stake in the [Staking](../staking/) section.

## Connecting to Testnet

When connecting to Creditcoin Testnet, the node must be run with additional options. First, it has to use the testnet chain specifications by passing the `--chain test` option. Testnet bootnodes must also be specified using the `--bootnodes` flag.

Testnet bootnodes:

* `/dns4/testnet-bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWG3eEuYxo37LvU1g6SSESu4i9TQ8FrZmJcjvdys7eA3cH`
* `/dns4/testnet-bootnode2.creditcoin.network/tcp/30333/p2p/12D3KooWLq7wCMQS3qVMCNJ2Zm6rYuYh74cM99i9Tm8PMdqJPDzb`
* `/dns4/testnet-bootnode3.creditcoin.network/tcp/30333/p2p/12D3KooWAKUrvmchoLomoouoN1sKfF9kq8dYtCVFvtPuvqp7wFBS`

Users wanting to explore testnet data can connect to the public testnet node provided by Creditcoin through [PolkadotJS Apps](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Frpc.testnet.creditcoin.network%2Fws#/explorer).

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>
