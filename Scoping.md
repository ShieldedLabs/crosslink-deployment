Scoping for Shielded Labs's first deployment of Crosslink
===

**Progress Tracking:** The top-level goals from this document are tracked as GitHub issues with the [Scoping](https://github.com/ShieldedLabs/crosslink-deployment/labels/Scoping) label.

# Rationale

## Why add Proof-of-Stake?

* Staking ZEC competes with selling ZEC, thus reducing the supply of ZEC for sale in the market, and the option to stake ZEC increases utility and therefore demand for ZEC. Reducing supply and increasing demand both put upward pressure on the price of ZEC. This is good because the price of ZEC is the fuel for the mission and attracts users.
* Proof-of-Stake adds economic finality, which protects users from being robbed, reduces and unifies [deposit times at centralized exchanges](https://zechub.wiki/using-zcash/custodial-exchanges) and other services and improves the safety and efficiency of bridges.
* Proof-of-Stake provides finality more efficiently than Proof-of-Work – at a lower cost in terms of both economics and energy usage. This makes Zcash both more secure (provide better security for the same cost) and more sustainable (provide security long-term even as the rate of issuance shrinks).
* Staking allows a larger number of users to participate actively in the network than mining does, and to become direct recipients of newly created ZEC from the blockchain. This increases the size and decentralization of the network of users and stakeholders.
* About the economic disadvantage of a smaller miner/validator/delegator competing with a larger operation:
  * In Proof-of-Work, smaller miners have a substantial economic disadvantage compared to larger mining operations.
  * In Proof-of-Stake, smaller validators have an economic disadvantage compared to larger validating services, but the disadvantage is not as pronounced as in Proof-of-Work mining.
  * In Proof-of-Stake, smaller delegators compete on a level playing field with larger delegators, earning roughly the same reward with roughly the same risk. (Note that delegators get less reward than validators.)

## Why use a Hybrid Proof-of-Stake plus Proof-of-Work system?

* Proof-of-Work provides a different and complementary kind of security that Proof-of-Stake doesn’t: preventing attackers from re-using resources in attacks. Hybrid finality provides a stronger kind of protection for users than pure-Proof-of-Stake finality, and thus lays a secure foundation for future scalability improvements.
* Proof-of-Work allows people to earn ZEC by mining, even if they don’t already own any ZEC and they can’t buy ZEC on an exchange.
* Proof-of-Work facilitates a ZEC->fiat->ZEC economy – rewards from mining have to be mostly spent on purchasing real-world goods and services like electricity and computing hardware (ASICs), which means transaction flows between ZEC and fiat. In contrast, rewards from staking can be reinvested directly into staking, which doesn’t require converting to fiat (although on the other hand it is good because it has those positive effects on supply and demand described above).
* Keeping Proof-of-Work in addition to adding Proof-of-Stake means that in addition to all of the stakers, we also keep miners as active participants in the network and as recipients of ZEC, increasing the total size and diversity of the Zcash network and the ZEC economy.


UX goals
---

This list of [UX Goals](https://github.com/ShieldedLabs/crosslink-deployment/labels/UX%20Goal) is tracked on GitHub.

* [GH #10](https://github.com/ShieldedLabs/crosslink-deployment/issues/10): Users justifiedly feel safe about the finality of their incoming Zcash transactions.
* [GH #11](https://github.com/ShieldedLabs/crosslink-deployment/issues/11): Services are willing to rely on incoming Zcash transaction finality. E.g. Coinbase re-enables market orders and reduces required confirmations to a nice small number like 10.
* [GH #14](https://github.com/ShieldedLabs/crosslink-deployment/issues/14): Other services that require finality, such as cross-chain bridges, are willing to rely on Zcash’s finality.
* [GH #15](https://github.com/ShieldedLabs/crosslink-deployment/issues/15): Unsophisticated users (who understand little about crypto and do not use specialized tools) delegate ZEC and get rewards from their mobile wallet.
* [GH #16](https://github.com/ShieldedLabs/crosslink-deployment/issues/16): Users run validators and get rewards. (It is okay if validator operators have to be users who understand a lot and can use specialized tools).

Deployment Goals
---

This list of [Deployment Goals](https://github.com/ShieldedLabs/crosslink-deployment/labels/Deployment%20Goals) is tracked on GitHub.

* [GH #18](https://github.com/ShieldedLabs/crosslink-deployment/issues/18): Zcash transactions come with a kind of finality which protects the users as much as possible against all possible attacks, and is sufficient for services such as cross-chain bridges and centralized exchanges.
* [GH #19](https://github.com/ShieldedLabs/crosslink-deployment/issues/19): Users can delegate their ZEC and earn rewards, safely and while needing to learn only the minimal number of new concepts.
    * Delegating to a validator does not enable the validator to steal your funds.
    * Delegating to a validator does not leak information that links the user's action to other information about them, such as their IP address, their other ZEC holdings that they are choosing not to stake, or their previous or future transactions.
* [GH #20](https://github.com/ShieldedLabs/crosslink-deployment/issues/20): The time-to-market and the risk of Shielded Labs's First Deployment of Crosslink is minimized: the benefits listed above start accruing as soon as safely possible.
* [GH #21](https://github.com/ShieldedLabs/crosslink-deployment/issues/21): Activating Crosslink on Zcash mainnet retains as much as possible of Zcash users' safety, security, privacy, and availability guarantees.

Trade-offs
---

Goals which we currently believe are not safely achievable in this first deployment without losing some of the above goals and requirements:
* Improving Zcash's bandwidth (number of transactions per time) or latency (time for a transaction).
* Deploying cross-chain interoperation such as the Inter-Blockchain Communication protocol (IBC) or Cross-Chain Interoperability Protocol (CCIP).
* Supporting a large number of validators so that any user who wants to run their own validator can do so.

[For a much more detailed and "living/work-in-progress" analysis of possible requirements, goals, and trade-offs, see this google doc: https://docs.google.com/document/d/1GZYQgQdzL1-GNJLWmt5CbTFXo1nuufkL7-gg7az_M2Q/edit?tab=t.0 .]
