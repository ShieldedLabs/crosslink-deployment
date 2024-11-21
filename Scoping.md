Scoping for Shielded Labs's first deployment of Crosslink
===

**Progress Tracking:** The top-level goals from this document are tracked as GitHub issues with the [Scoping](https://github.com/ShieldedLabs/crosslink-deployment/labels/Scoping) label.

Why Hybrid Proof-of-Work/Proof-of-Stake?
---
* It reduces supply of ZEC by locking up staked ZEC and increases demand for ZEC by giving people something else to do with it. Both reducing supply and increasing demand put upward pressure on the price of ZEC. This is good because the price of ZEC is the fuel for the mission and attracts users.
* It adds finality, which protects users from being robbed (with hybrid protection), reduces deposit times at CEXes and other services, and enables bridges.
* It lays the foundation for future improvements, such as cross-chain interop and scalability.

UX goals
---

This list of [UX Goals](https://github.com/ShieldedLabs/crosslink-deployment/labels/UX%20Goal) is tracked on GitHub.

* [GH #10](https://github.com/ShieldedLabs/crosslink-deployment/issues/10): Users justifiedly feel safe about the finality of their incoming Zcash transactions.
* [GH #11](https://github.com/ShieldedLabs/crosslink-deployment/issues/11): Services are willing to rely on incoming Zcash transaction finality. E.g. Coinbase re-enables market orders and reduces required confirmations to a nice small number like 10. All or most services rely on the same canonical (protocol-provided) finality instead of enforcing [their own additional delays or conditions](https://zechub.wiki/using-zcash/custodial-exchanges), and so the user experience is that transaction finality is predictable and recognizable across services.
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
