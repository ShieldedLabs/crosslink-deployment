Scoping for Shielded Labs's first deployment of Crosslink
===

Why Hybrid Proof-of-Work/Proof-of-Stake?
---
* It reduces supply of ZEC by locking up staked ZEC and increases demand for ZEC by giving people something else to do with it. Both reducing supply and increasing demand put upward pressure on the price of ZEC. This is good because the price of ZEC is the fuel for the mission and attracts users.
* It adds finality, which protects users from being robbed (with hybrid protection), reduces deposit times at CEXes and other services, and enables bridges.
* It lays the foundation for future improvements, such as cross-chain interop and scalability.
* Proof of Stake provides security more efficiently – at a lower cost in terms of economics and in terms of energy usage – than Proof of Work.

UX goals
---
* Users justifiedly feel safe about the finality of their incoming Zcash transactions.
* Services are willing to rely on incoming Zcash transaction finality. E.g. Coinbase re-enables market orders and reduces required confirmations to a nice small number like 10.
* Other services that require finality, such as cross-chain bridges, are willing to rely on Zcash’s finality.
* Unsophisticated users (who understand little about crypto and do not use specialized tools) delegate ZEC and get rewards from their mobile wallet.
* Users run validators and get rewards. (It is okay if validator operators have to be users who understand a lot and can use specialized tools).

Requirements
---
* Zcash transactions come with a kind of finality which protects the users as much as possible against all possible attacks, and is sufficient for services such as cross-chain bridges and centralized exchanges.
* Users can delegate their ZEC and earn rewards, safely and while needing to learn only the minimal number of new concepts.
    * Delegating to a validator does not enable the validator to steal your funds.
    * Delegating to a validator does not leak information that links the user's action to other information about them, such as their IP address, their other ZEC holdings that they are choosing not to stake, or their previous or future transactions.
* The time-to-market and the risk of Shielded Labs's First Deployment of Crosslink is minimized: the benefits listed above start accruing as soon as safely possible.
* Activating Crosslink on Zcash mainnet retains as much as possible of Zcash users's safety, security, privacy, and availability guarantees.

Trade-offs
---

Goals which we currently believe are not safely achievable in this first deployment without losing some of the above goals and requirements:
* Improving Zcash's bandwidth (number of transactions per time) or latency (time for a transaction).
* Deploying cross-chain interoperation such as the Inter-Blockchain Communication protocol (IBC) or Cross-Chain Interoperability Protocol (CCIP).
* Supporting a large number of validators so that any user who wants to run their own validator can do so.

[For a much more detailed and "living/work-in-progress" analysis of possible requirements, goals, and trade-offs, see this google doc: https://docs.google.com/document/d/1GZYQgQdzL1-GNJLWmt5CbTFXo1nuufkL7-gg7az_M2Q/edit?tab=t.0 .]
