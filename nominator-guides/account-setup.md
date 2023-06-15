# Account Setup

Nominators are recommended to set up separate stash and controller accounts.

You can generate your stash and controller account via any of the recommended methods, which are detailed on the [wallets](../wallets/) section.

If you'd like to redirect payments to a wallet that is neither the controller nor the stash account, set one up. We strongly recommend against using an exchange address as the recipient for any staking rewards.

## Stash and Controller Security <a href="#stash-and-controller-security" id="stash-and-controller-security"></a>

When it comes to Creditcoin's "controller" and "stash" keys, they serve different purposes and can be likened to hot and cold wallets in the context of cryptocurrency storage.

The controller key, similar to a hot wallet, is meant for regular use and manual transactions, controlled directly by the user. It should hold some CTC for fees but not large amounts. On the other hand, the stash key, like a cold wallet, is intended for long-term storage of significant funds and should be kept offline, like a piece of paper in a safe or protected by hardware security layers.

The stash key is bonded to the controller key, allowing the controller to manage and make decisions with the weighted influence of the stash. However, to maintain security, it's crucial to protect the controller key and consider changing it periodically to prevent potential unauthorized access and malicious actions.
