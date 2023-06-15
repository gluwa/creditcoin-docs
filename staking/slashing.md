# Slashing

In Creditcoin, slashing serves as a means to discourage malicious behavior by imposing penalties on validators who act against the network's interests. Validators who partake in harmful activities may face a reduction in their staked tokens through slashing. This mechanism plays a vital role in upholding the network's security and integrity by incentivizing validators to prioritize the network's well-being.

In the event of a slash, any nominators who were backing the slashed validator will also have their stake slashed. This creates a reputational incentive for validators to maintain good behaviour which is required to attract nominator stake, and simultaneously, incentives nominators to thoroughly evaluate any validators before backing them, resulting in increased overall network security. Regardless of whether you nominate validators directly or through a nomination pool, your stake is susceptible to slashing.

#### Types of Offences <a href="#types-of-offences" id="types-of-offences"></a>

There are three types of offences in the Creditcoin network which can lead to a validator getting slashed:

* Inactivity: being offline during a designated time slot
* Block production: producing more than one block in a designated time slot
* Block finalization: finalizing blocks on two different versions of the chain (forks) in the same time slot

Each offence has its own penalty calculation. Inactivity goes from a minor warning that chills the validator (removes it from the active set) up to slashing 7% of the their total stake if several validators go offline during a single era.

<figure><img src="../.gitbook/assets/image (6).png" alt=""><figcaption></figcaption></figure>

Validators who commit production or finalization offences get between 0% and 100% of their stake slashed depending on how many offences of the same type where recorded in that particular era.

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

**Slashing calculations**

| **Offence**                | **Formula**                                                                                    | **Range**       |
| -------------------------- | ---------------------------------------------------------------------------------------------- | --------------- |
| Inactivity                 | `min((3 * (offending_validators - (total_validators / 10 + 1))) / total_validators, 1) * 0.07` | 0% (chill) - 7% |
| Block production offence   | `(3 * offender_count) / total_validator_count) ^ 2`                                            | 0% - 100%       |
| Block finalization offence | `(3 * offender_count) / total_validator_count) ^ 2`                                            | 0% - 100%       |

&#x20;
