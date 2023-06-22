# Creditcoin-CLI (beta)

Creditcoin CLI is a terminal-based general purpose tool developed by the Creditcoin team and includes all the basic features expected for a blockchain wallet. Users can create accounts, send and receive CTC and stake without the need for a graphical interface.



> ![:warning:](https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/atlassian/warning\_32.png)
>
> Creditcoin CLI is under active development and might not be straight forward for non-technical users. If you have no systems administrator or CLI tools experience, consider using a GUI wallet. For detailed information about Creditcoin CLI refer to the documentation on Github or the `--help` command.

**Creating accounts**

Create accounts using the `new` command and write down the newly generated mnemonic phrase and store it securely.&#x20;

```bash
creditcoin-cli new
```

**Sending & Receiving CTC**

The CLI tool also allows sending and receiving CTC. To send use the `send` command like so.

```bash
creditcoin-cli send --amount <amount> --to <address>
```

To receive CTC send funds to the address shown when entering the `show-address` command.

```bash
creditcoin-cli show-address
```

**Staking**

You can stake CTC using the terminal by using the `bond` command and setting up an amount and a controller account.

```bash
creditcoin-cli bond \
    --controller <controller-address> \
    --amount <amount> \
    --reward-destination <stake|stash|controller>
```

After bonding CTC, the controller can either set up a new validator node or nominate validators.

> ![:white\_check\_mark:](https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/standard/caa27a19-fc09-4452-b2b4-a301552fd69c/32x32/2705.png)
>
> If you want to set up a [Validator ](../../validator-guides/)or become a [Nominator](../../nominator-guides/), read the detailed guides and make sure you understand both risks and responsibilities.
