# Creditcoin-CLI (beta)

Creditcoin CLI is a terminal-based general-purpose tool developed by the Creditcoin team and includes all the basic features required to administer nominator and validator accounts. Users can create accounts, send and receive CTC and stake without the need for a graphical interface.



> ![:warning:](https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/atlassian/warning\_32.png)
>
> Creditcoin CLI is under active development and might not be straight forward for non-technical users. If you have no systems administrator or CLI tools experience, consider using a GUI wallet. For detailed information about Creditcoin CLI refer to the documentation on Github or the `--help` command.

**Creating accounts**

Create accounts using the `new` command and write down the newly generated mnemonic phrase and store it securely.&#x20;

```bash
creditcoin-cli new
```

**Sending & Receiving CTC**

The CLI tool also allows sending and receiving CTC. To send use the `send` command like so. It will prompt you for the seed phrase of the account from which funds will be sent.

```bash
creditcoin-cli send --amount <amount> --to <address>
```

To receive CTC, you can provide the sender with the receiving account's address.

**Computing an Account's Address**

To compute an account's address from its seed phrase, use the `show-address` command. The `show-address` command will prompt you for the seed phrase.

```bash
creditcoin-cli show-address
```

#### Checking your Balance

You can check the balance of an account using the command below. This is an unauthenticated command. Ensure the CLI is connected to a node you trust to provide you with accurate data. You can check the balance of any account without incurring transaction fees.

```
creditcoin-cli balance -a <address>
```

**Staking**

You can stake CTC via a terminal by using the `bond` command with an amount and a controller address. This transaction is signed by your stash account and designates a controller account to act on its behalf. You will be prompted for your stash account's seed phrase.

```bash
creditcoin-cli bond \
    --controller <controller-address> \
    --amount <amount> \
    --reward-destination <address>
```

After bonding CTC, the controller can either set up a new validator node or nominate validators.

> ![:white\_check\_mark:](https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/caa27a19-fc09-4452-b2b4-a301552fd69c/32x32/2705.png)
>
> If you want to set up a [Validator ](../../validator-guides/)or become a [Nominator](../../nominator-guides/), read the detailed guides and make sure you understand both risks and responsibilities.
