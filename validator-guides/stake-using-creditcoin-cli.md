# Stake using Creditcoin-CLI

## Using the Docker image <a href="#using-a-docker-container" id="using-a-docker-container"></a>

Creditcoin-CLI comes installed inside the official Creditcoin Docker image. Run the container and set up name for it.

```bash
docker run -n creditcoin-validator gluwa/creditcoin:latest
```

Once it is running, use Creditcoin-CLI via the `docker exec` command.

```bash
docker exec creditcoin-validator creditcoin-cli --help
```

## Creating Accounts

Create two accounts using the `new` command and write down their seed phrases.

```bash
docker exec creditcoin-validator creditcoin-cli new
# Creating new seed phrase...
# Seed phrase: chalk adapt cancel oyster bright foster bean mushroom home acquire salon roof
docker exec creditcoin-validator creditcoin-cli new
# Creating new seed phrase...
# Seed phrase: follow actual seven pill kit side apart column cattle kiss fat write
```

Use `show-address` to fund both accounts. One will be the Stash account and hold all tokens meant for staking. The other one will be the Controller, a secondary account that will manage the validator.

```bash
docker exec creditcoin-validator creditcoin-cli show-address -s "follow actual seven pill kit side apart column cattle kiss fat write"
# Account address: 5CYEdiz9X5o5yrMMK8HM6Tb9LmzX1P4PcJekZrECeHv9UKH4
```

## Validator Wizard

Creditcoin-CLI provides a simple Wizard to set up validators. After running the wizard, it should show us the complete validator setup options and prompt us to continue.

```bash
docker exec creditcoin-validator creditcoin-cli wizard -ss <stash-seed-phrase> -cs <controller-seed-phrase> -a <ctc-amount>
# 🧙 Running staking wizard...
# Using the following parameters:
# 💰 Stash account: 5CGBosx2Fw34u9jJtSgEQkoNTtHkPLKgsfjJiE3mDSWb44MW
# 🕹️  Controller account: 5E1tpiU3SnunxwbtvTc7U7gykNYspTZu9yqTcch2pHamAvw5
# 🪙  Amount to bond: 10000 CTC
# 🎁 Reward destination: Staked
# 📡 Node URL: ws://127.0.0.1:9945
# 💸 Commission: 0
# 🔐 Blocked: No
# Continue? (y/n): y
```

After continuing, the Wizard will create al required extrinsics and communicate with the node to pair it with the stash and controller accounts.

Once the transactions are sent, the new validator should be in the waiting queue.

The `status` command should show as following:

```bash
docker exec creditcoin-validator creditcoin-cli status -a 5CGBosx2Fw34u9jJtSgEQkoNTtHkPLKgsfjJiE3mDSWb44MW
# Bonded:  true
# Controller:  5E1tpiU3SnunxwbtvTc7U7gykNYspTZu9yqTcch2pHamAvw5
# Validating:  true
# Waiting:  true
# Active:  false
# Next unbonding chunk: None
```

## Manual Setup

Setting a validator can also be done by sending each required command manually.

Create two accounts using the `new` command and write down their seed phrases.

```bash
docker exec creditcoin-validator creditcoin-cli new
# Creating new seed phrase...
# Seed phrase: chalk adapt cancel oyster bright foster bean mushroom home acquire salon roof
docker exec creditcoin-validator creditcoin-cli new
# Creating new seed phrase...
# Seed phrase: follow actual seven pill kit side apart column cattle kiss fat write
```

Bond CTC and designate your Controller account using the `--controller` or `-c` option.

```bash
docker exec creditcoin-validator creditcoin-cli bond -s <controller-seed-phrase> -c <controller-address> -a <ctc-amount>
```

Set the validator node keys using the controller account. The rotate flag specifies that the node will generate new keys. Existing keys can be used with the `--keys <key-string>` option.

```bash
docker exec creditcoin-validator creditcoin-cli set-keys -s <controller-seed-phrase> --rotate
```

Once keys are set up, the last step is signaling the network the intention to validate. Use the `--commission` option to set up a portion of the block reward that will not be shared with nominators.

```bash
docker exec creditcoin-validator creditcoin-cli validate -s <controller-seed-phrase> --commission <commission-percent>
```

## Stopping a Validator

Stop a running validator with the `chill` command. This will remove the validator from the active/waiting set in the next session.

```bash
docker exec creditcoin-validator creditcoin-cli chill -s <controller-seed-phrase>
```

## Unbonding CTC

To unbond locked CTC, validators must first mark their tokens for unbonding, then wait for the unlocking period to end and finally withdraw the unbonded funds.

```bash
docker exec creditcoin-validator creditcoin-cli unbond -s <controller-seed-phrase> -a <amount>
```

The status command shows when the next unlocking chunk will be available to withdraw.

```bash
docker exec creditcoin-validator creditcoin-cli status -a <stash-address>
# Bonded:  true
# Controller:  5E1tpiU3SnunxwbtvTc7U7gykNYspTZu9yqTcch2pHamAvw5
# Validating:  true
# Waiting:  false
# Active:  true
# Next unbonding chunk: 1000 CTC in 6 minutes, 5 seconds
```

After the time has passed, withdraw the funds.

```bash
docker exec creditcoin-validator creditcoin-cli withdraw-unbonded -s <controller-seed-phrase>
```
