# Stake using PolkadotJS

It is recommended that you have two different accounts for your controller and stash. Make sure they both have enough funds to pay transaction fees. The Stash account should be kept safe since its private keys will be the ones securing the tokens.

## **1. Run a Validator Node**

Run your synced node as a validator by adding the `--validator` flag.

### **Using the built binary**

```bash
./target/release/creditcoin-node \
  --validator
  --prometheus-external \
# (optional) opt in to telemetry
  --telemetry-url "wss://telemetry.polkadot.io/submit/ 0" \
# node to connect to on boot, in order to join the network
  --bootnodes "/dns4/bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWAEgDL126EUFxFfdQKiUhmx3BJPdszQHu9PsYsLCuavhb" "/dns4/bootnode2.creditcoin.network/tcp/30333/p2p/12D3KooWSQye3uN3bZQRRC4oZbpiAZXkP2o5UZh6S8pqyh24bF3k" "/dns4/bootnode3.creditcoin.network/tcp/30333/p2p/12D3KooWFrsEZ2aSfiigAxs6ir2kU6en4BewotyCXPhrJ7T1AzjN" \
# REPLACE <yourhostname or ip> with the public IP address or host name that your node can be reached at
  --public-addr "/dns4/<yourhostname or ip>/tcp/30333" \
# we want to connect to the mainnet
  --chain mainnet \
# the base path to store the node's data
  --base-path /data \
# the port to use for node-to-node communication
  --port 30333
```

### **Using the container**

```bash
docker run \
  -p 30333:30333 \
  -v <your local data path>:/data \
# Enter testnet/mainnet image
  gluwa/creditcoin:latest \
  --validator \
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
# the base path to store the node's data
  --base-path /data \
# the port to use for node-to-node communication
  --port 30333
```

## **2. Rotate Keys with Polkadot-JS**

Go to the RPC section and submit an `author_rotateKeys` request to your node. Make sure you are connected to your own node and not a public endpoint. You will get back a `0x` prefixed string.

<figure><img src="../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

## **3. Bond & Validate**

Go to the [Staking](https://polkadot.js.org/apps/?rpc=wss://rpc.mainnet.creditcoin.network/ws#/staking) section on Polkadot-JS APPS. Click on "Account Actions", and then the "+ Validator" button. (For Testnet, [use this link](https://polkadot.js.org/apps/?rpc=wss://rpc.testnet.creditcoin.network/ws#/staking))

Select your stash and controller accounts using the dropdown menu. Enter the amount of CTC you wish to bond and the payment destination.

> ![:warning:](https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/atlassian/warning\_32.png)
>
> ! If you bond all of your CTC, you won’t be able to send any transactions.. Make sure you leave some tokens unbonded to pay for CTC transactions fees.

<figure><img src="../.gitbook/assets/image (11).png" alt=""><figcaption></figcaption></figure>

Enter your validator fee and select if you want to receive nominations or not. Then click on Bond & Validate.

<figure><img src="../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

After signing and sending the extrinsic, the validator should appear in the waiting queue.

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption></figcaption></figure>

## **Stopping a Validator**

To stop your validator, simply click on the Stop button. You will be prompted to submit a new transaction that will remove your validator from the candidate set.

<figure><img src="../.gitbook/assets/image (13).png" alt=""><figcaption></figcaption></figure>

&#x20;
