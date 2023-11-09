---
description: Frequently asked questions about the Creditcoin Network.
---

# FAQ

## What is Creditcoin?

Creditcoin is the world’s leading L1 real-world asset infrastructure chain, designed to match borrowers with lenders and record credit transactions on-chain. With over 3 million credit transactions recorded to-date, Creditcoin is creating a global ledger of credit history and loan performance, facilitating transparency and reducing information asymmetries between market participants to pave the way for a new generation of on-chain RWA credit markets.

Having integrated with a number of fintech lenders, connecting them directly to global DeFi investors, the Creditcoin network has helped thousands of borrowers, businesses, and investors secure capital financing, build credit history, and make global RWA investments.

Creditcoin ($CTC) is the utility token of the Creditcoin Network, and is spent as a transaction fee to complete and record loan cycles on the Creditcoin Network. \
To find out more about Creditcoin and why we need it, head [here](https://creditcoin.org/blog/creditcoin-explained/).

## Who is Creditcoin designed for?

Creditcoin is an institutional-grade interoperable blockchain designed to help real-world financial institutions access on-chain lending liquidity from DeFi investors. By integrating with Creditcoin and recording their credit performance on-chain via Credal these institutions can leverage two key advantages:&#x20;

Trustless Financial Auditing: By transparently securing immutable credit performance data on-chain, Creditcoin helps to reduce information asymmetries and counterparty risks between investors and borrowers, helping to facilitate efficient global investment and capital flows.&#x20;

Web3 Liquidity: By providing on-chain infrastructure to raise capital directly from Web3, Creditcoin can help financial institutions access quick liquidity from global investors, whilst democratizing RWA markets for everyday crypto investors.&#x20;

If you’re an institution interested in finding out what Creditcoin can do for you, then contact our team at [team@creditcoin.org](mailto:team@creditcoin.org)&#x20;

For a visualization of the Creditcoin Ecosystem and its users, see the graphic below.

<figure><img src="https://lh5.googleusercontent.com/admeKrKSs6JSGzn68CGvyuf6F657ZodftWAzCxTtdLjNuAt_4cQFHOLUErcb6M-71dHvYrLjrSaexTFj50Q8XPJO3O3ZPmsQ0D3kbDc9tAGAazfWt7wZc9v_EprsGSVpo5HkpcYN7g__pylsgFCKtaE" alt=""><figcaption></figcaption></figure>

### What changed with the Creditcoin 2.0+ update?

The Creditcoin 2.0+ transitioned the Network from Proof-of-Work (PoW) to Nominated Proof-of-Stake (NPoS), in addition to making a number of Tokenomics adjustments and other performance-related improvements.&#x20;

NPoS is a modified form of Proof-of-Stake, the consensus mechanism found in Ethereum and most other L1 chains, excluding Bitcoin. Modeled on Polkadot’s NPoS, Creditcoin’s NPoS implementation offers a number of advantages over PoW including increased energy efficiency, scalability, real-world performance, decentralization and security.&#x20;

The 2.0+ update also made a number of tokenomics adjustments. The average block time was reduced from 60s -> 15s in order to increase settlement speeds. The block reward was reduced from 28 -> 2 in order to reduce token inflation, and reflect the reduced validation costs associated with NPoS vs PoW. Finally, the token cap was removed.

## What is Credal? What advantages does it offer?

[Credal](https://credal.io/) is the API service for Creditcoin, enabling third parties to interact with the Creditcoin mainnet to write loans or retrieve data etc. It functions similarly to Infura for Ethereum. With partnered credit providers, such as Aella, using Credal to interact with the Creditcoin mainnet and record loans. It is also used by our block explorer to retrieve loan data.

Credal simplifies third-party interaction with Creditcoin, allowing relevant entities to integrate with Creditcoin and leverage its inherent advantages – including transparent, privacy-preserving, auditing capabilities, data security and on-chain interoperability.

For more information on how Credal can help scale your credit operations, head [here](http://credal.io/).

## How does Creditcoin enforce repayment and/or punish default?

Creditcoin is a reputational ledger, relying on reputational incentives to encourage repayment. If a party fails to pay back the agreed interest in the agreed timeframe, then the Creditcoin Network will simply record that as a non-repayment failure, damaging that parties credit score.

This doesn’t mean that Creditcoin loans are necessarily unsecured. Creditcoin can work in conjunction with off-chain enforcement mechanisms such as legal agreements, or through on-chain smart contracts which enforce repayment. However, Creditcoin does not itself inflict punishment for defaulting outside of reputational damages.

## How does the Creditcoin Network use CTC?

Creditcoin Network users must pay a CTC network transaction fee to complete certain transactions in the loan cycle, with each stage creating a verifiable trail of credit history per user that’s tied to their wallet address. Only write transactions cost CTC, read-only interactions are free. The image below provides a summary of Creditcoin's loan cycle and transaction types.

<figure><img src="https://lh3.googleusercontent.com/HwdBUS5_ChtfOHxpyU6pPvcVtLacI9aMigYldVsq4zifZ3mXPVg-4gWvL6jA_8EmqGnlWSEiZC9bh2SZQLer3vwgOgtjRy8FMpTn3wjugr17NCyV5Er-nXJXC19GgUcIZ9Vs8QaYzxdcWx_1M-_-VAo" alt=""><figcaption><p>The Creditcoin Loan Process</p></figcaption></figure>

Loan transactions matched and recorded on Creditcoin are completed on other chains. Currently Bitcoin and ERC-20 are supported, though more networks will be supported in future, including Polygon. For a full technical breakdown of Creditcoin and each stage of the loan cycle, please [consult our Whitepaper](https://creditcoin.org/white-paper).

## Does Creditcoin have a Block Explorer?

Yes we do. Link below.&#x20;

[Creditcoin Explorer](https://explorer.creditcoin.org/)

## What is the relationship between Creditcoin, Gluwa and Aella?

​[Gluwa](https://gluwa.com/) is a technology provider of Creditcoin, handling development on behalf of the Creditcoin Foundation, as well as providing general infrastructure, such as back-end wallet services, to Creditcoin Ecosystem members.\
[Aella](https://aellaapp.com/) is the first institutional user of the Creditcoin blockchain, having integrated its operations with Creditcoin via Credal in [June 2022](https://medium.com/creditcoin-foundation/creditcoin-x-aella-integration-live-c8b8eb3b606d).

## What consensus algorithm does Creditcoin use?

Creditcoin uses a Nominated Proof-of-Stake (NPoS) consensus algorithm to ensure network security. This is a modified form of Proof-of-Stake designed to encourage greater decentralization and security. NPoS allows for two different types of staking users:

**Validators**: Compete to get elected into the active set and write new blocks. Once elected, a Validator is responsible for verifying and producing new blocks, earning CTC rewards for doing so. Validators must run their own node and can earn a staking commission fee.&#x20;

**Nominators**: Vote for Validators to get elected by staking their CTC. In return, they earn a share of any elected Validator’s rewards, equivalent to their staking percentage minus any commission fees.

When a Validator node acts maliciously or otherwise engages in poor behavior, any CTC backing them may be slashed, incentivizing both Validators and Nominators to engage in honest voting and behavior.&#x20;

If you’re interested in staking your CTC to help secure the network and earn CTC rewards, please consult the relevant documentation [here](https://docs.creditcoin.org/creditcoin-miners-manual).&#x20;

## Are there any risks associated with staking?

In Creditcoin’s NPoS staking system, dishonest Validators, and any Nominators backing them, are at risk of having their staked CTC slashed in the case of dishonest behavior. Therefore, it is important to make sure that you choose your validators carefully.

## When was the Creditcoin Mainnet released?

The Creditcoin 2.0 Mainnet on Substrate was officially released on [June 23, 2022](https://medium.com/creditcoin-foundation/creditcoin-2-0-official-launch-f286ff6436a4). For technical details, please review the Creditcoin Github repositories at [https://github.com/gluwa/Creditcoin](https://github.com/gluwa/Creditcoin).

The original Creditcoin Mainnet on Hyperledger Sawtooth was released on April 4, 2019. This version is no longer maintained.

## What are the details of Creditcoin’s initial token allocation?

The initial distribution of CTC (ERC-20) aka G-CRE tokens are as follows:

* Investors (Genesis allocation; 6-month to 3-year linear vesting) – 200M CTC, For funding network development, business development, partnerships, and support. Any unsold tokens were remitted to the Creditcoin Foundation with a vesting period of 6 years.
* Gluwa, Inc. (Genesis allocation; 6-year linear vesting) – 300M CTC, For R\&D, deployment, business development, marketing, distribution, and administration costs.
* Creditcoin Foundation (Genesis allocation; 6-year linear vesting) – 100M CTC, For long-term network governance, partner support, academic grants, public works, and community building

Please note that with the 2.0+ update, there is no longer a fixed supply of CTC. Please consult the Tokenomics FAQ to find out more.

## Did Creditcoin have an ICO or token sale?

A private token sale was conducted starting 01/09/2017 in the form of a Creditcoin SAFT. The token sale had a soft cap of $10m USD and a hard cap of $30m USD.

All 200 million available Creditcoin tokens were purchased and introduced into the market following this sale.

## What is the difference between $CTC and $G-CRE?

The Creditcoin ecosystem involves two distinct tokens which represent the same underlying asset – $CTC and $G-CRE.

**$CTC** - The mainnet token used for network transaction fees and is earned as a staking reward. Utility is restricted exclusively to the Creditcoin mainnet where it is used to pay loan cycle transactions fees.

**$G-CRE** - Based on the ERC-20 Ethereum Network and not directly usable on the Creditcoin mainnet. $G-CRE is used for vesting and trading, and can be exchanged into $CTC using a one-way 1:1 hook.

**$G-CRE** is listed on exchanges, but exchange tickers denote it as $CTC.

## Are $CTC or $G-CRE tokens tradable on exchanges?

At this time, only $G-CRE, which is Creditcoin's ERC-20 vesting and trading token, is tradable on exchanges. Exchanges list $G-CRE using the $CTC ticker.

## Which exchanges is $G-CRE listed on?

$G-CRE is currently listed on these exchanges:

* **CTC/BTC**
  * [Upbit](https://upbit.com/exchange?code=CRIX.UPBIT.BTC-CTC)
  * [Bithumb](https://www.bithumb.com/trade/order/CTC\_BTC)
  * [OKX](https://www.okex.com/markets/spot-info/ctc-usdt)
  * [Bittrex](https://bittrex.com/Market/Index?MarketName=BTC-CTC)
  * [KuCoin](https://www.kucoin.com/trade/CTC-BTC?rcode=rPH7VCS)
* **CTC/USDT**
  * [OKX](https://www.okex.com/markets/spot-info/ctc-usdt)
  * [MEXC](https://www.mexc.com/exchange/CTC\_USDT)
  * [Poloniex](https://poloniex.com/spot/CTC\_USDT/)
  * [Gate.io](https://gate.io/trade/ctc\_usdt)
  * [Bybit](https://www.bybit.com/en-US/trade/spot/CTC/USDT)
  * [Huobi Global](https://www.huobi.com/en-us/exchange/ctc\_usdt)
* **CTC/KRW**
  * [Bithumb](https://www.bithumb.com/trade/order/CTC\_KRW)

More listings are planned. See [https://coinmarketcap.com/currencies/creditcoin/markets/](https://coinmarketcap.com/currencies/creditcoin/markets/) for a complete list of active exchanges.

## How can I swap $G-CRE for the $CTC mainnet coin?

There is an online web app provided by Gluwa which supports G-CRE -> CTC swaps. The web app link is available [here](https://creditcoin.org/swap/intro).&#x20;

## What is the total amount of $CTC issued?

The maximum supply is uncapped, with an issuance rate of 2 CTC per block. This equates to roughly 8 CTC every minute. You can view the total current supply using the block explorer [here](https://explorer.creditcoin.org/). Please also bear in mind that CTC fees are burned when used in a transaction, reducing the overall supply.

## What is the Creditcoin Network transaction fee?

The Creditcoin Network transaction fee is a fee payable in CTC whenever a write-transaction occurs on the mainnet. CTC transaction fees are variable, dynamically scaling according to the network load and the relative computational cost of each transaction.&#x20;

Different transaction types have different base ‘weights’ from which transaction fees are calculated. These weights are calculated according to their relative computation cost. Generally speaking, the more ‘read’ and ‘writes’ a transaction needs to perform, the more expensive it is. You can view a breakdown of Creditcoin transaction weighting [here](https://github.com/gluwa/creditcoin/blob/main/pallets/creditcoin/src/weights.rs).

To understand more about how fees are calculated on substrate read [this](https://docs.substrate.io/v3/runtime/weights-and-fees/).&#x20;

As part of Creditcoin 2.0, transaction fees are now also burned when used in a transaction, creating deflationary CTC supply.&#x20;

Previously, fees were locked and then returned to the user after a year. Please note that this is no longer the case.

## How do I stake $CTC to earn rewards?

Please consult the Creditcoin documentation for detailed instructions on how to become a Validator or Nominator. The documentation is available at: [https://docs.creditcoin.org/creditcoin-miners-manual](https://docs.creditcoin.org/creditcoin-miners-manual)​

## Can I stake my $CTC?

Yes, you can stake mainnet CTC as part of the Creditcoin consensus mechanism and earn CTC rewards for doing so. Please consult the Creditcoin documentation for detailed instructions on how to start earning rewards by becoming a Validator or Nominator.

For a full CTC staking guide, read [this](staking/).&#x20;

**Validators**: Validators must run their own node and compete to get elected via staking. They earn Validator rewards and can also earn an additional staking commission fee.&#x20;

**Nominators**: Vote for Validators and earn a share of any elected Validator’s rewards, equivalent to their staking percentage, minus any commission fees.

## What do you call the smallest unit of Creditcoin?

The smallest unit of Creditcoin is called “[credo](https://en.m.wikipedia.org/wiki/Credo)” (pronounced \[ˈkɾeːdoː], Latin for "I believe").
