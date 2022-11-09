# DeAudit - A decentralized Audit marketplace on Polygon using web3.storage

## Inspiration

Owing to the immutable nature of blockchain technology, it is impossible to update the code after its deployment. Placing smart contracts without adequate audits could lead to undesirable situations like differences in the contract's intended performance, gas leakage, and more.

- 47% of the web3 hacks in the first half of 2022 were due to contract vulnerabilities.
- Only 52% of the exploited web3 projects were audited.
- Helps earn users/investors' trust for the product and the idea.

Auditing isn't an easy process. Auditing wait times on top audit firms are 9-12 months and are expensive. We need something that is more participative and allows for new and yet-unproven security auditors. This is the motivation behind building DeAudit, a decentralized audit marketplace that turns the auditing process into a prediction marketplace.

## How DeAudit works

#### 1. Select a jury

A jury is usually a reputed, security engineer. This jury doesn’t do the audit itself but only signs off a reported vulnerability as a real bug. There are 5 jury members selected for every audit. They control a 3/5 multisig that approves a detected bug once it is reported by an auditor. They receive 5% of the total audit spend.

#### 2. The contract is deployed for auditing

The contract must be deployed on-chain to make the code immutable.

#### 3. Pools are created

Once the contract is deployed, 2 betting pools are created. Called _NoBugs_ and _YesBugs_ - representing a betting pool that says there are no severe bugs in this contract v/s yes there are bugs in this contract.

#### 4. Pools are equally funded

To kick start the marketplace, the person requesting the audit must fund both pools.

#### 5. Auditors audit and fund pools

A security auditor looks at the deployed contract and judges whether there are bugs in this contract or not.

If they’re confident there are no severe bugs; they may add money to the _NoBugs_ pool.

#### 6. Money starts streaming from YesBugs to NoBugs

Until a bug has been reported, the money from the _YesBugs_ pool starts streaming to _NoBugs_ pool, so the _YesBugs_ pool will be exhausted in 30 days.

#### 7a. Bug report

If a security engineer finds a bug, they may report it to the jury.

The jury will vote with their signature on whether the bug is severe. If the jury accepts the bug as a severe bug, the NoBugs pool is liquidated, and all the money from _NoBugs_ pool is distributed to the people who funded the _YesBugs_ pool. This distribution happens proportionally to

- When the funder puts money in the _YesBugs_ pool (earlier you make a bet, more is your reward if true)

- Amount put in as the bet (larger your bet that there are bugs, the more the reward)

- 5% goes to the jury members equally

#### 7b. No bugs reported

If the size of _NoBugs_ pool is greater than 95% of the summation of the pools, the _NoBugs_ pool can be liquidated. All the people who bet that there are no bugs are rewarded by the same ratios presented in 7a.
