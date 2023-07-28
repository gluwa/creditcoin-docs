# Environments

A node can be configured to connect to different Creditcoin networks. Each network has different configurations and use cases.

| Attributes    | Devnet                                        | Testnet                                       | Mainnet                           |
| ------------- | --------------------------------------------- | --------------------------------------------- | --------------------------------- |
| Overview      | Local/public development environment          | Public testing environment                    | Live production environment       |
| Users         | Developers                                    | Developers & testers                          | End users                         |
| Function      | To develop new features & improvements        | To test new features & improvements           | To secure credit history on-chain |
| Tokens        | Test tokens with no real world economic value | Test tokens with no real world economic value | Real tokens with economic value   |
| Chain history | Wiped frequently                              | Wiped occasionally                            | Preserved                         |

The network configuration is specified using the `--chain` flag and the `--bootnodes` flag, which specifies the initial nodes to connect to. Currently, only the `test` network chain specs include bootnodes. The `main` and `dev` networks bootnodes must be specified manually.

Example:

```bash
./target/release/creditcoin-node --chain main --bootnodes "/dns4/bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWAEgDL126EUFxFfdQKiUhmx3BJPdszQHu9PsYsLCuavhb"
```

## **ChainSpecs**

Creditcoin networks are configured using a `ChainSpec`. The `ChainSpec` is a JSON file that defines the initial configuration of the network. To use a `ChainSpec`, use the `--chain` flag when starting the node.

* Mainnet: `--chain main`
* Testnet: `--chain test`
* Devnet: `--chain dev`

## **Bootnodes**

Bootnodes are nodes that are always on and can be used to bootstrap new nodes and discover other nodes in the network. To use a bootnode, use the `--bootnodes` flag when starting the node followed by the bootnode's address.
