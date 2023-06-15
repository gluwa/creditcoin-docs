# Subkey

You can use the following subcommands with the `subkey` command. For more detailed information about using Subkey, refer to their [official documentation](https://docs.substrate.io/reference/command-line-tools/subkey/).

| Command             | Description                                                                                                                     |
| ------------------- | ------------------------------------------------------------------------------------------------------------------------------- |
| `generate`          | Generates a random account key.                                                                                                 |
| `generate-node-key` | Generates a random node `libp2p` secret key. You can save the secret key to a file or display it as standard output (`stdout`). |
| `help`              | Displays usage information for `subkey` or for a specified subcommand.                                                          |
| `inspect`           | Displays the public key and SS58 address for the secret URI you specify.                                                        |
| `inspect-node-key`  | Displays the peer ID that corresponds with the secret node key in the file name you specify.                                    |
| `sign`              | Signs a message with the secret key you specify.                                                                                |
| `vanity`            | Generates a seed that provides a vanity address.                                                                                |
| `verify`            | Verifies the signature for a message is valid for the public or secret key you specify.                                         |
