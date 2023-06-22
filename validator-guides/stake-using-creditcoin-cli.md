# Stake using Creditcoin-CLI

## Running from the Docker image <a href="#using-a-docker-container" id="using-a-docker-container"></a>

Make sure your Creditcoin Node container is running and use Creditcoin-CLI via the `docker exec` command.

```bash
docker exec -it creditcoin-validator creditcoin-cli --help
```

{% hint style="warning" %}
Security notes:&#x20;

* When using docker, employ `docker exec` as specified in these docs to keep sensitive values out of the container's logs on your system.
* Only use the Creditcoin CLI to administer a validator from its own machine or container. Do not use the Creditcoin CLI to remotely administer a validator even on the same LAN or virtual network. Connections to the node, from the Creditcoin CLI, are made over unencrypted and unauthenticated websockets and are only safe for use on the loopback interface. (i.e `localhost`, `127.0.0.1`)
* Remember that, when using any terminal or command line tool, commands entered in your terminal window are visible to other users and services on your system. Only enter secrets like seed phrases when prompted by the Creditcoin CLI.
{% endhint %}

## Creating Accounts

Create two accounts using the `new` command and save their seed phrases somewhere secure.

```bash
docker exec -it creditcoin-validator creditcoin-cli new
```

Each output should look like the following:

```
Creating new seed phrase...
Seed phrase: follow actual seven pill kit side apart column cattle kiss fat write
```

Use `show-address` to fund both accounts. One will be the Stash account and hold all tokens meant for staking. The other one will be the Controller, a secondary account that will manage the validator.

```bash
docker exec -it creditcoin-validator creditcoin-cli show-address
# ? Specify seed phrase ›
# Account address: 5CYEdiz9X5o5yrMMK8HM6Tb9LmzX1P4PcJekZrECeHv9UKH4
```

## Validator Wizard

Creditcoin-CLI provides a simple Wizard to set up validators. It will prompt you for the previously generated seed phrases as needed. After launching the wizard and providing it with our seed phrases, it will show us the complete validator setup options and prompt us to continue.

{% hint style="warning" %}
Security note:

* Accounts' private keys are derived form these seed phrases.
* Every account must have a unique seed phrase.
* Remember to use separate accounts (i.e. new seed phrases) for testnet and mainnet validators.
{% endhint %}

```bash
docker exec -it creditcoin-validator creditcoin-cli wizard -a <ctc-amount>
```

It will show the current staking settings, make sure to check them before continuing.

```
🧙 Running staking wizard...
Using the following parameters:
💰 Stash account: 5CGBosx2Fw34u9jJtSgEQkoNTtHkPLKgsfjJiE3mDSWb44MW
🕹️  Controller account: 5E1tpiU3SnunxwbtvTc7U7gykNYspTZu9yqTcch2pHamAvw5
🪙  Amount to bond: 10000 CTC
🎁 Reward destination: Staked
📡 Node URL: ws://127.0.0.1:9945
💸 Commission: 0
🔐 Blocked: No
Continue? (y/n): y
```

After continuing, the Wizard will create all required extrinsics and communicate with the node to pair it with the stash and controller accounts.

Once the transactions are sent, the new validator should be in the waiting queue.

Use the`status` command to get information about the status of a particular validator by entering its Stash address.

```bash
docker exec -it creditcoin-validator creditcoin-cli status -a 5CGBosx2Fw34u9jJtSgEQkoNTtHkPLKgsfjJiE3mDSWb44MW
```

The validator status will be shown:

```
Bonded:  true
Controller:  5E1tpiU3SnunxwbtvTc7U7gykNYspTZu9yqTcch2pHamAvw5
Validating:  true
Waiting:  true
Active:  false
Next unbonding chunk: None
```

If the validator shows up as `Waiting` the setup has been successful and it will become active if it gets enough backing.

## Manual Setup

Setting a validator can also be done by sending each required command manually.

After creating two accounts, first bond CTC using your Stash account and designate your Controller account using the `--controller` or `-c` option.

```bash
docker exec creditcoin-validator creditcoin-cli bond -c <controller-address> -a <ctc-amount>
```

Set the validator node keys using the controller account. The rotate flag specifies that the node will generate new keys. Existing keys can be used with the `--keys <key-string>` option.

```bash
docker exec creditcoin-validator creditcoin-cli set-keys --rotate
```

Once keys are set up, the last step is signaling the network the intention to validate. Use the `--commission` option to set up a portion of the block reward that will not be shared with nominators.

```bash
docker exec creditcoin-validator creditcoin-cli validate --commission <commission-percent>
```

## Distributing Rewards

It is conventionally the validator operator's responsibility to trigger the reward distribution at the end of every era. The address of the stash account doubles as the validator's ID when distributing rewards.

Remember, you can compute the stash account's address by running the following and providing the stash account's seed phrase when prompted.

```bash
docker exec -it creditcoin-validator creditcoin-cli show-address
```

With the stash address in hand, run the `distribute-rewards` command.

```bash
docker exec creditcoin-validator creditcoin-cli distribute-rewards --validator-id <validator-stash-address>
```

## Stopping a Validator

Stop a running validator with the `chill` command. This will remove the validator from the active/waiting set in the next session.

```bash
docker exec creditcoin-validator creditcoin-cli chill
```

## Unbonding CTC

To unbond locked CTC, validators must first mark their tokens for unbonding, then wait for the unlocking period to end and finally withdraw the unbonded funds.

```bash
docker exec creditcoin-validator creditcoin-cli unbond -a <amount>
```

The status command shows when the next unlocking chunk will be available to withdraw.

```bash
docker exec -it creditcoin-validator creditcoin-cli status -a <stash-address>
```

```
# Bonded:  true
# Controller:  5E1tpiU3SnunxwbtvTc7U7gykNYspTZu9yqTcch2pHamAvw5
# Validating:  true
# Waiting:  false
# Active:  true
# Next unbonding chunk: 1000 CTC in 6 minutes, 5 seconds
```

After the unbonding period has passed, withdraw the funds.

```bash
docker exec creditcoin-validator creditcoin-cli withdraw-unbonded
```
