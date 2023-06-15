# Using a Docker Container

## Sync Chain Data <a href="#sync-chain-data.1" id="sync-chain-data.1"></a>

Ensure Docker is installed  and run the `creditcoin-node` Docker container.

To use the latest Testnet, make sure you are using the \`[gluwa/creditcoin:2.222.0-testnet](https://hub.docker.com/layers/gluwa/creditcoin/2.222.0-testnet/images/sha256-3817a742a4a56235f8b951acf0e9bcd83f5a595320c34fb9dd0ee74c60b18504?context=explore)\` docker image and the bootnodes from the [Testnet Environment page](../environments/testnet.md)&#x20;

```bash
docker run \
  -p 30333:30333 \
  -v <your local data path>:/data \
# Enter testnet/mainnet image
  gluwa/creditcoin:latest \
# allow prometheus metrics to be scraped
  --prometheus-external \
# (optional) opt in to telemetry
  --telemetry-url "wss://telemetry.polkadot.io/submit/ 0" \
# node to connect to on boot, in order to join the network
  --bootnodes "/dns4/bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWAEgDL126EUFxFfdQKiUhmx3BJPdszQHu9PsYsLCuavhb" "/dns4/bootnode2.creditcoin.network/tcp/30333/p2p/12D3KooWSQye3uN3bZQRRC4oZbpiAZXkP2o5UZh6S8pqyh24bF3k" "/dns4/bootnode3.creditcoin.network/tcp/30333/p2p/12D3KooWFrsEZ2aSfiigAxs6ir2kU6en4BewotyCXPhrJ7T1AzjN" \
# REPLACE <yourhostname or ip> with the public IP address or host name that your node can be reached at
  --public-addr "/dns4/<yourhostname or ip>/tcp/30333" \
# we want to connect to the mainnet
  --chain mainnet \
# we want to run a validator node  
  --validator \ 
# the base path to store the node's data
  --base-path /data \
# the port to use for node-to-node communication
  --port 30333
```

Here is an example command to run a validator that connects to the Creditcoin Testnet:

```bash
docker run \
-p 30333:30333 \
-v ~/chain_data:/data \
gluwa/creditcoin:2.222.0-testnet \
--bootnodes "/dns4/testnet-bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWG3eEuYxo37LvU1g6SSESu4i9TQ8FrZmJcjvdys7eA3cH" "/dns4/testnet-bootnode2.creditcoin.network/tcp/30333/p2p/12D3KooWLq7wCMQS3qVMCNJ2Zm6rYuYh74cM99i9Tm8PMdqJPDzb" "/dns4/testnet-bootnode3.creditcoin.network/tcp/30333/p2p/12D3KooWAKUrvmchoLomoouoN1sKfF9kq8dYtCVFvtPuvqp7wFBS" \
--chain test \
--validator \
--base-path /data \
--port 30333
```
