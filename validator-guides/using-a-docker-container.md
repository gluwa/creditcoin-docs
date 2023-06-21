# Using a Docker Container

## Sync Chain Data <a href="#sync-chain-data.1" id="sync-chain-data.1"></a>

Ensure Docker is installed (or [install it in your OS of choice](https://docs.docker.com/engine/install/)) and run the `creditcoin-node` Docker image.

> Docker should automatically pull the specified `gluwa/creditcoin` image. If not, you can try pulling it yourself from DockerHub by running `docker pull gluwa/creditcoin:2.222.1-testnet` and then re-running the command below.

> PowerShell does not support comments on multiline commands, please use the uncommented version.

{% tabs %}
{% tab title="Bash" %}
```bash
docker run \
 --name creditcoin-validator \
 -p 30333:30333 \
 -v <your local data path>:/creditcoin-node/data  \
 gluwa/creditcoin:2.222.1-testnet `# Enter testnet image` \
 --name "validator name" `# name the validator` \
 --telemetry-url "wss://telemetry.creditcoin.network/submit/ 0" `# (optional) opt in to telemetry` \
 --public-addr "/dns4/<yourhostname or ip>/tcp/30333" `# REPLACE <yourhostname or ip> with the public IP address or host name that your node can be reached at
` \
--chain test `# we want to connect to the testnet` \
 --bootnodes "/dns4/testnet-bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWG3eEuYxo37LvU1g6SSESu4i9TQ8FrZmJcjvdys7eA3cH" "/dns4/testnet-bootnode2.creditcoin.network/tcp/30333/p2p/12D3KooWLq7wCMQS3qVMCNJ2Zm6rYuYh74cM99i9Tm8PMdqJPDzb" "/dns4/testnet-bootnode3.creditcoin.network/tcp/30333/p2p/12D3KooWAKUrvmchoLomoouoN1sKfF9kq8dYtCVFvtPuvqp7wFBS" \
--validator `# we want to run a validator node` \
--base-path /creditcoin-node/data `# the base path to store the node's data` \
--port 30333 # the port to use for node-to-node communication
```
{% endtab %}

{% tab title="PowerShell" %}
<pre class="language-powershell"><code class="lang-powershell">docker run `
  --name creditcoin-validator `
  -p 30333:30333 `
  -v &#x3C;your local data path>:/creditcoin-node/data `
# Enter testnet image
  gluwa/creditcoin:2.222.1-testnet `
# name the validator
  --name "validator name" `
# (optional) opt in to telemetry
  --telemetry-url "wss://telemetry.creditcoin.network/submit/ 0" `
# REPLACE &#x3C;yourhostname or ip> with the public IP address or host name that your node can be reached at
  --public-addr "/dns4/&#x3C;yourhostname or ip>/tcp/30333" `
# we want to connect to the testnet
  --chain test `
# we want to run a validator node
<strong>  --bootnodes "/dns4/testnet-bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWG3eEuYxo37LvU1g6SSESu4i9TQ8FrZmJcjvdys7eA3cH" "/dns4/testnet-bootnode2.creditcoin.network/tcp/30333/p2p/12D3KooWLq7wCMQS3qVMCNJ2Zm6rYuYh74cM99i9Tm8PMdqJPDzb" "/dns4/testnet-bootnode3.creditcoin.network/tcp/30333/p2p/12D3KooWAKUrvmchoLomoouoN1sKfF9kq8dYtCVFvtPuvqp7wFBS" `
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
  gluwa/creditcoin:2.222.1-testnet `
  --name "validator name" `
  --telemetry-url "wss://telemetry.creditcoin.network/submit/ 0" `
  --public-addr "/dns4/<yourhostname or ip>/tcp/30333" `
  --chain test `
  --bootnodes "/dns4/testnet-bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWG3eEuYxo37LvU1g6SSESu4i9TQ8FrZmJcjvdys7eA3cH" "/dns4/testnet-bootnode2.creditcoin.network/tcp/30333/p2p/12D3KooWLq7wCMQS3qVMCNJ2Zm6rYuYh74cM99i9Tm8PMdqJPDzb" "/dns4/testnet-bootnode3.creditcoin.network/tcp/30333/p2p/12D3KooWAKUrvmchoLomoouoN1sKfF9kq8dYtCVFvtPuvqp7wFBS" `
  --validator `
  --base-path /creditcoin-node/data `
  --port 30333
```
{% endtab %}
{% endtabs %}
