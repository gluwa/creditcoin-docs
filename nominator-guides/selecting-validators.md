# Selecting Validators

Nominating validators on Creditcoin is an active role. If any of your elected validators misbehave, nominators may lose their funds due to slashing. Even if offences do not trigger slashing, they might still cause the validator to be chilled, meaning that any backing nominators will stop earning rewards.

Users who do not wish to actively participate in validator election, but who nevertheless want to earn staking rewards, can instead join a Nomination Pool. By doing so, users effectively delegate their votes to the Nomination Pool operator, who will assign them to validator candidates.

## Nominating Best Practices <a href="#nominating-best-practices" id="nominating-best-practices"></a>

**1. Choosing more than one Validator**

Since stake is allocated after the validator election, nominators do not need to manage the allocation of their staking quantities themselves. As long as one or more of a nominator's chosen validators enters the active set, all of that nominators stake will be actively used to back their chosen validators.

Nominators who only choose to back a small number of validators risk getting no rewards if none of them are chosen to be part of the active set. Inversely, a nominator’s stake distribution is likely to result in better rewards if they choose more validators to support. Therefore, it is always advisable for a nominator to choose as many trustworthy validators as possible.

> ![:info:](https://pf-emoji-service--cdn.us-east-1.prod.public.atl-paas.net/atlassian/info\_32.png)&#x20;
>
> For more information about the Validator Selection process refer to the[ Validator Elections](../staking/validator-elections.md) section.

**2. Check who is operating the validator**

If a validator has set its identity, you'll see their details on the Community tab of the Staking Dashboard. Besides a displayed name, a validator can also indicate their email, website, Twitter account, or something else.

**3. Check the commission**

A validator’s block rewards are shared with any backing nominators, but, the validator can also set a pre-defined commission they receive before any leftover rewards are shared. This rate can vary greatly.

Validators that set up a 100% commission do not share any rewards with their nominators, while validators that choose a 0% commission will share all rewards with their nominators. You can use the Staking Dashboard to sort validators based on their commission fee and filter out those with high ones.

**4. Make sure the validator is not oversubscribed**

Only the top 512 nominators for a specific validator get paid. The validators over this limit are marked red warning sign on the Staking Dashboard. These validators can be active, and if you choose them, you may actively support them in an era. However, if your stake is less than the 512 largest nominators, you won't receive any rewards for it.

It's also a good idea to avoid validators with a high number of nominators, even if they're not oversubscribed, because they may get oversubscribed soon.

**5. Add good validators to your Favourites**

When you have decided on your validators, add them to your Favourites: click on the heart icon on the Staking Dashboard. This will allow you to quickly select them as your nominations later.
