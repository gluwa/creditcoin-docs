# Using a Docker Container

{% hint style="info" %}
Before continuing, please make sure you have setup a Stash and Controller address, as mentioned in the [Account Setup](../nominator-guides/account-setup.md) section.
{% endhint %}

## Sync Chain Data <a href="#sync-chain-data.1" id="sync-chain-data.1"></a>

Ensure Docker is installed (or [install it in your OS of choice](https://docs.docker.com/engine/install/)) and run the `creditcoin-node` Docker image.

> Docker should automatically pull the specified `gluwa/creditcoin` image. If not, you can try pulling it yourself from DockerHub by running `docker pull gluwa/creditcoin:2.231.0-mainnet` and then re-running the command below.

> PowerShell does not support comments on multiline commands, please use the uncommented version.

{% tabs %}
{% tab title="Bash" %}
```bash
docker run \
 --name creditcoin-validator \
 -p 30333:30333 \
 -v <your local data path>:/creditcoin-node/data  \
 gluwa/creditcoin:2.231.0-mainnet `# Enter latest mainnet image` \
 --name "validator name" `# name the validator` \
 --telemetry-url "wss://telemetry.creditcoin.network/submit/ 0" `# (optional) opt in to telemetry` \
 --public-addr "/dns4/<yourhostname or ip>/tcp/30333" `# REPLACE <yourhostname or ip> with the public IP address or host name at which your node can be reached` \
 --chain main `# we want to connect to the mainnet` \
 --bootnodes "/dns4/bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWAEgDL126EUFxFfdQKiUhmx3BJPdszQHu9PsYsLCuavhb" "/dns4/bootnode2.creditcoin.network/tcp/30333/p2p/12D3KooWSQye3uN3bZQRRC4oZbpiAZXkP2o5UZh6S8pqyh24bF3k" "/dns4/bootnode3.creditcoin.network/tcp/30333/p2p/12D3KooWFrsEZ2aSfiigAxs6ir2kU6en4BewotyCXPhrJ7T1AzjN" \
 --validator `# we want to run a validator node` \
 --base-path /creditcoin-node/data `# the base path to store the node's data` \
 --port 30333 # the port to use for node-to-node communication
```
{% endtab %}

{% tab title="Uncommented Bash" %}
```
docker run \
 --name creditcoin-validator \
 -p 30333:30333 \
 -v <your local data path>:/creditcoin-node/data  \
 gluwa/creditcoin:2.231.0-mainnet \
 --name "validator name" \
 --telemetry-url "wss://telemetry.creditcoin.network/submit/ 0" \
 --public-addr "/dns4/<yourhostname or ip>/tcp/30333" \
 --chain main \
 --bootnodes "/dns4/bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWAEgDL126EUFxFfdQKiUhmx3BJPdszQHu9PsYsLCuavhb" "/dns4/bootnode2.creditcoin.network/tcp/30333/p2p/12D3KooWSQye3uN3bZQRRC4oZbpiAZXkP2o5UZh6S8pqyh24bF3k" "/dns4/bootnode3.creditcoin.network/tcp/30333/p2p/12D3KooWFrsEZ2aSfiigAxs6ir2kU6en4BewotyCXPhrJ7T1AzjN" \
 --validator \
 --base-path /creditcoin-node/data \
 --port 30333
```
{% endtab %}

{% tab title="PowerShell" %}
<pre class="language-powershell"><code class="lang-powershell">docker run `
  --name creditcoin-validator `
  -p 30333:30333 `
  -v &#x3C;your local data path>:/creditcoin-node/data `
# Enter testnet image
  gluwa/creditcoin:2.231.0-mainnet `
# name the validator
  --name "validator name" `
# (optional) opt in to telemetry
  --telemetry-url "wss://telemetry.creditcoin.network/submit/ 0" `
# REPLACE &#x3C;yourhostname or ip> with the public IP address or host name that your node can be reached at
  --public-addr "/dns4/&#x3C;yourhostname or ip>/tcp/30333" `
# we want to connect to the testnet
  --chain main `
# we want to run a validator node
<strong>  --bootnodes "/dns4/bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWAEgDL126EUFxFfdQKiUhmx3BJPdszQHu9PsYsLCuavhb" "/dns4/bootnode2.creditcoin.network/tcp/30333/p2p/12D3KooWSQye3uN3bZQRRC4oZbpiAZXkP2o5UZh6S8pqyh24bF3k" "/dns4/bootnode3.creditcoin.network/tcp/30333/p2p/12D3KooWFrsEZ2aSfiigAxs6ir2kU6en4BewotyCXPhrJ7T1AzjN" `
</strong>  --validator `
# the base path to store the node's data
  --base-path /creditcoin-node/data `
# the port to use for node-to-node communication
  --port 30333
</code></pre>
{% endtab %}

{% tab title="Uncommented Powershell" %}
```powershell
docker run `
  --name creditcoin-validator `
  -p 30333:30333 `
  -v <your local data path>:/creditcoin-node/data `
  gluwa/creditcoin:2.231.0-mainnet `
  --name "validator name" `
  --telemetry-url "wss://telemetry.creditcoin.network/submit/ 0" `
  --public-addr "/dns4/<yourhostname or ip>/tcp/30333" `
  --chain test `
  --bootnodes "/dns4/bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWAEgDL126EUFxFfdQKiUhmx3BJPdszQHu9PsYsLCuavhb" "/dns4/bootnode2.creditcoin.network/tcp/30333/p2p/12D3KooWSQye3uN3bZQRRC4oZbpiAZXkP2o5UZh6S8pqyh24bF3k" "/dns4/bootnode3.creditcoin.network/tcp/30333/p2p/12D3KooWFrsEZ2aSfiigAxs6ir2kU6en4BewotyCXPhrJ7T1AzjN" `
  --validator `
  --base-path /creditcoin-node/data `
  --port 30333
```
{% endtab %}
{% endtabs %}

In the command above, notice the `-v` flag that takes a local directory as the first part of the parameter. It's import that docker has the ability to write to this directory, otherwise you will see errors such as `Error: Service(Client(Backend("IO Error: Permission denied (os error 13)")))`. Your command will likely use a path similar to `-v /home/validator/data:/creditcoin-node/data`.

Here is an example command to run a validator that connects to the Creditcoin **Testnet**:

```bash
docker run \
-p 30333:30333 \
-v ~/chain_data:/data \
gluwa/creditcoin:2.223.0-testnet \
--bootnodes "/dns4/testnet-bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWG3eEuYxo37LvU1g6SSESu4i9TQ8FrZmJcjvdys7eA3cH" "/dns4/testnet-bootnode2.creditcoin.network/tcp/30333/p2p/12D3KooWLq7wCMQS3qVMCNJ2Zm6rYuYh74cM99i9Tm8PMdqJPDzb" "/dns4/testnet-bootnode3.creditcoin.network/tcp/30333/p2p/12D3KooWAKUrvmchoLomoouoN1sKfF9kq8dYtCVFvtPuvqp7wFBS" \
--chain test \
--validator \
--base-path /data \
--port 30333
```
