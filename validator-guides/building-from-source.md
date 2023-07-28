# Building from Source

#### Install Rust <a href="#install-rust" id="install-rust"></a>

Install the latest version of Rust.

`curl https://sh.rustup.rs -sSf | sh -s -- -y`

If Rust is already installed, make sure to add the nightly version and the WebAssembly target:

```bash
# Ensure the current shell has cargo
source ~/.cargo/env

# Update the Rust toolchain
rustup default stable
rustup update

# Add the nightly and WebAssembly targets:
rustup update nightly
rustup target add wasm32-unknown-unknown --toolchain nightly
```

Verify your installation.

`rustup show`

#### Install dependencies <a href="#install-dependencies" id="install-dependencies"></a>

Make sure you have all the necessary dependencies for compiling and running the Creditcoin node software.

`sudo apt install make clang pkg-config libssl-dev build-essential protobuf-compiler`

You may need to install & configure [Network Time Protocol (NTP) Client](https://en.wikipedia.org/wiki/Network\_Time\_Protocol).

#### Building & Installing the Creditcoin binary <a href="#building-and-installing-the-creditcoin-binary" id="building-and-installing-the-creditcoin-binary"></a>

You will be building the latest `creditcoin` binary from [gluwa/creditcoin](https://github.com/gluwa/creditcoin) repository on Github using the source code in the `main` branch.

Download the repository by cloning it.

`git clone https://github.com/gluwa/creditcoin`

Move into the `creditcoin` folder and checkout to the `main` branch by running the following command.

`cd creditcoin`
`git checkout main`

Build the binary with `cargo`.

`cargo build -r`

This step might take 10 - 40 minutes to finish.

#### Sync Chain Data <a href="#sync-chain-data" id="sync-chain-data"></a>

Synchronize your node by running the binary inside the `target/release` folder.

```bash
./target/release/creditcoin-node \
  --prometheus-external \
# (optional) opt in to telemetry
  --telemetry-url "wss://telemetry.creditcoin.io/submit/ 0" \
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
