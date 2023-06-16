# Using a Docker Container

## Sync Chain Data <a href="#sync-chain-data.1" id="sync-chain-data.1"></a>

Ensure Docker is installed  and run the `creditcoin-node` Docker container.

```bash
docker run \
  -p 30333:30333 \
  -v <your local data path>:/data \
# Enter testnet image
  gluwa/creditcoin:2.222.1-testnet \
# node to connect to on boot, in order to join the network
  --bootnodes "/dns4/testnet-bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWG3eEuYxo37LvU1g6SSESu4i9TQ8FrZmJcjvdys7eA3cH" "/dns4/testnet-bootnode2.creditcoin.network/tcp/30333/p2p/12D3KooWLq7wCMQS3qVMCNJ2Zm6rYuYh74cM99i9Tm8PMdqJPDzb" "/dns4/testnet-bootnode3.creditcoin.network/tcp/30333/p2p/12D3KooWAKUrvmchoLomoouoN1sKfF9kq8dYtCVFvtPuvqp7wFBS" \
# REPLACE <yourhostname or ip> with the public IP address or host name that your node can be reached at
  --public-addr "/dns4/<yourhostname or ip>/tcp/30333" \
# we want to connect to the testnet
  --chain test \
# we want to run a validator node  
  --validator \ 
# the base path to store the node's data
  --base-path /data \
# the port to use for node-to-node communication
  --port 30333
```
