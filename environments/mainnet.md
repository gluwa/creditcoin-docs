# Mainnet

Mainnet is the main network where CTC has real-world economic value. Most Creditcoin software, including the Creditcoin node, will connect to Mainnet by default unless the user specifies another network.

It is not recommended to test new features on Mainnet. It is more appropiate to test using [Testnet](testnet.md).

## Connecting to Mainnet

Creditcoin software connects to mainnet by default, but recommeded to select some of the official bootnodes when syncing a new node.

Mainnet bootnodes:

* `/dns4/bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWAEgDL126EUFxFfdQKiUhmx3BJPdszQHu9PsYsLCuavhb`
* `/dns4/bootnode2.creditcoin.network/tcp/30333/p2p/12D3KooWSQye3uN3bZQRRC4oZbpiAZXkP2o5UZh6S8pqyh24bF3k`
* `/dns4/bootnode3.creditcoin.network/tcp/30333/p2p/12D3KooWFrsEZ2aSfiigAxs6ir2kU6en4BewotyCXPhrJ7T1AzjN`


These can by added by passing the `--bootnodes` flag when running Creditcoin.

```
--bootnodes "<bootnode1-url" "bootnode2-url"
```
