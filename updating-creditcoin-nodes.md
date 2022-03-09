---
description: >-
  We recommend using the latest production images for better mining experience.
  Also, you can take advantage of a snapshot to upstart your syncing process.
---

# Updating Creditcoin Nodes

## Option 1: Update Creditcoin Images <a href="#e110" id="e110"></a>

_Recommended for regular users_

Note: In the commands provided below you may need to replace `Server/docker-compose.yaml` with your .yaml file name and path for your node.&#x20;

If you run into any issues, download the latest version of the docker-compose files from [Github](https://github.com/gluwa/CreditcoinDockerCompose-Mainnet), then follow the instructions in [Creditcoin Miner's Manual](creditcoin-miners-manual/) to reconfigure your node.

1. Stop your existing docker containers:

```
$ docker-compose -f Server/docker-compose.yaml down
```

2\. Run the following commands:

```bash
$ docker-compose -f Server/docker-compose.yaml pull
```

3\. Start your existing docker containers:

```
$ docker-compose -f Server/docker-compose.yaml up
```

{% hint style="info" %}
Have a Problem Updating?

Check if your images in your .yaml file(s) are set to these:

```yaml
gluwa/creditcoin-client:1.7
gluwa/creditcoin-validator:1.7
gluwa/creditcoin-processor:1.7
gluwa/creditcoin-gateway:1.7
gluwa/sawtooth-rest-api:1.7
```
{% endhint %}

## Option 2: Manually update several lines in your existing `docker-compose.yaml` file <a href="#e110" id="e110"></a>

_Recommended for advanced users_

1\. In the REST API container section, replace the image line with:

```yaml
image: gluwa/sawtooth-rest-api:1.7
```

2\. Processor container section, do the following:\
&#x20;a. Remove  `- rest-api` from the `depends_on` section\
&#x20;b. Replace the entrypoint lines with:

```yaml
    entrypoint: ./ccprocessorLinux.out tcp://validator:4004 tcp://gateway:55555
```

3\. In the Validator container section, replace the existing seeds lines with the following:

```yaml
                --seeds tcp://node-000.creditcoin.org:8800 \
                --seeds tcp://node-001.creditcoin.org:8800 \
                --seeds tcp://node-002.creditcoin.org:8800 \
                --seeds tcp://node-003.creditcoin.org:8800 \
```

## Download Snapshot <a href="#04db" id="04db"></a>

We strongly recommend using the published blockchain snapshot to avoid any potential problems.

**Direct Download:**\
[http://dl.creditcoin.org/latestblocks/snapshot-03-09-2022.tar.gz](http://dl.creditcoin.org/latestblocks/snapshot-03-09-2022.tar.gz)

**CLI download examples:**\
`wget http://dl.creditcoin.org/latestblocks/snapshot-03-09-2022.tar.gz`\
`aria2c -x5 http://dl.creditcoin.org/latestblocks/snapshot-03-09-2022.tar.gz`

**Torrent Download:**\
[http://dl.creditcoin.org/latestblocks/snapshot-03-09-2022.tar.gz.torrent](http://dl.creditcoin.org/latestblocks/snapshot-03-09-2022.tar.gz.torrent)

**Torrent Magnet** Link**:**

```
magnet:?xt=urn:btih:2fc772aa5d5fbcef162611c81dae3ea4bd0b7130&xt=urn:btmh:1220e132c6ad8c4600d6edda0275102f01ccf690cc864b58ba825389e023117cbe5a&dn=snapshot-03-09-2022.tar.gz&tr=udp%3a%2f%2ftracker.opentrackr.org%3a1337%2fannounce&tr=udp%3a%2f%2ftracker.openbittorrent.com%3a6969%2fannounce&tr=http%3a%2f%2fopenbittorrent.com%3a80%2fannounce&ws=http%3a%2f%2fdl.creditcoin.org%2flatestblocks%2fsnapshot-03-09-2022.tar.gz
```

### Snapshot Details <a href="#snapshot-details-1" id="snapshot-details-1"></a>

* Timestamp: 3/9/2022
* Latest Block: 1124015
* File Name: snapshot-03-09-2022.tar.gz
* File Size: 90.0 GB
* SHA-256 File Hash: d694d018e39074efdcfee4681004e53271c0587bfd42edb64a7a39b56095f3a2

## Use Snapshot

Note: In the commands provided below you may need to replace `Server/docker-compose.yaml` with your the .yaml file name and path for your node, or download the latest version of the docker-compose files from [Github](https://github.com/gluwa/CreditcoinDockerCompose-Mainnet), and then follow the instructions in [Creditcoin Miner's Manual](creditcoin-miners-manual/) to reconfigure your node.

### Linux

1. Stop the node\
   `sudo docker-compose -f Server/docker-compose.yaml down`
2. [Download blockchain snapshot](https://docs.creditcoin.org/updating-creditcoin-nodes#04db) and place it in `/`
3. Remove the existing blockchain files\
   `sudo bash -c "rm /var/lib/docker/volumes/server_validator-block-volume/_data/*"`
4. Extract the snapshot\
   `sudo tar xzvf /ccSnapshot-2021.10.16_961837.tar.gz --directory /var/lib/docker/volumes/server_validator-block-volume/`
5. Restart the node\
   `sudo docker-compose -f Server/docker-compose.yaml up`

### Windows

1. [Download blockchain snapshot](https://docs.creditcoin.org/updating-creditcoin-nodes#04db) and note the location (e.g. `C:\temp`)&#x20;
2. Stop the Creditcoin docker containers:\
   `> docker-compose -f Server/docker-compose.yaml down`
3. In a new PowerShell or Command Prompt  window, create a temporary container, and mount Docker root to /host:\
   `> docker run -it -v /:/host ubuntu /bin/sh`
4. Get the new container name (It will be something like "recursing\_lamport"):\
   `> docker container ls`
5. Copy the snapshot to the docker container (Where "recursing\_lamport" is the container name from step 3)\
   `> docker cp "C:\temp\snapshot-03-09-2022.tar.gz" recursing_lamport:/`
6. In the window from step 3, extract the blockchain snapshot: `$ sudo tar xzvf /snapshot-03-09-2022.tar.gz --directory /host/var/lib/docker/volumes/server_validator-block-volume/`
7. Restart the Creditcoin docker containers\
   `> docker-compose -f Server/docker-compose.yaml up`

### Mac OS X

1. [Download blockchain snapshot](https://docs.creditcoin.org/updating-creditcoin-nodes#04db) and note the location (e.g.  `/home/user`)&#x20;
2. Stop the Creditcoin docker containers:\
   `> docker-compose -f Server/docker-compose.yaml down`
3. In a new Terminal window, create a temporary container and mount Docker root to /host:\
   `> docker run -it -v /:/host ubuntu /bin/sh`
4. Get the new container name (It will be something like "recursing\_lamport"):\
   `> docker container ls`
5. Copy the snapshot to the docker container (Where "recursing\_lamport" is the container name from step 3)\
   `$ docker cp "/home/user/snapshot-03-09-2022.tar.gz" recursing_lamport:/`
6. In the window from step 3, extract the blockchain snapshot: `$ sudo tar xzvf /snapshot-03-09-2022.tar.gz --directory /host/var/lib/docker/volumes/server_validator-block-volume/`
7. Restart the Creditcoin docker containers\
   `> docker-compose -f Server/docker-compose.yaml up`
