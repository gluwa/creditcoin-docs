# Building from Source

#### Install Rust <a href="#install-rust" id="install-rust"></a>

Install the latest version of Rust.

`curl https://sh.rustup.rs -sSf | sh -s -- -y`

If Rust is already installed, make sure to add the nightly version and the WebAssembly target:

```bash
# Ensure the current shell has cargo
source ~/.cargo/env

# Update the Rust toolchain
rustup default nightly-2023-04-16
rustup update nightly-2023-04-16

# Add the nightly and WebAssembly targets:
rustup target add wasm32-unknown-unknown --toolchain nightly-2023-04-16
```

Verify your installation.

`rustup show`

#### Install dependencies <a href="#install-dependencies" id="install-dependencies"></a>

Make sure you have all the necessary dependencies for compiling and running the Creditcoin node software.

`sudo apt install make clang pkg-config libssl-dev build-essential`

You may need to install & configure [Network Time Protocol (NTP) Client](https://en.wikipedia.org/wiki/Network\_Time\_Protocol).

#### Building & Installing the Creditcoin binary <a href="#building-and-installing-the-creditcoin-binary" id="building-and-installing-the-creditcoin-binary"></a>

You will be building the latest `creditcoin` binary from [gluwa/creditcoin](https://github.com/gluwa/creditcoin) repository on Github using the source code in the `main` branch.

Download the repository by cloning it.

`git clone https://github.com/gluwa/creditcoin`

Move into the `creditcoin` folder and checkout to the `testnet` branch by running the following command.

`cd creditcoin`\
`git checkout testnet`

Build the binary with `cargo`.

`cargo build -r`

This step might take 10 - 40 minutes to finish.

#### Sync Chain Data <a href="#sync-chain-data" id="sync-chain-data"></a>

Synchronize your node by running the binary inside the `target/release` folder.

```bash
./target/release/creditcoin-node \
  --validator
# node to connect to on boot, in order to join the network
  --bootnodes "/dns4/testnet-bootnode.creditcoin.network/tcp/30333/p2p/12D3KooWG3eEuYxo37LvU1g6SSESu4i9TQ8FrZmJcjvdys7eA3cH" "/dns4/testnet-bootnode2.creditcoin.network/tcp/30333/p2p/12D3KooWLq7wCMQS3qVMCNJ2Zm6rYuYh74cM99i9Tm8PMdqJPDzb" "/dns4/testnet-bootnode3.creditcoin.network/tcp/30333/p2p/12D3KooWAKUrvmchoLomoouoN1sKfF9kq8dYtCVFvtPuvqp7wFBS" \
# REPLACE <yourhostname or ip> with the public IP address or host name that your node can be reached at
  --public-addr "/dns4/<yourhostname or ip>/tcp/30333" \
# we want to connect to the mainnet
  --chain test \
# the base path to store the node's data
  --base-path /data \
# the port to use for node-to-node communication
  --port 30333

```
