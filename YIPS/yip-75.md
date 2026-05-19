---
yip: 75
title: Launch V3
author: V3 Protocol Team & V3 Secret Admirers Group
discussions-to: https://gov.yearn.fi/t/yip-75-launch-v3/13591
status: Approved
created: 2023-08-15
---

## Simple Summary
Launch the full V3 system - making the latest generation of yield generating vaults and strategies permissionlessly deployable by anyone.

## Abstract
If adopted, this proposal seeks to:

* Ratify the Design Specification of V3 and endorse its deployment.
* Specify parameters and initial configurations.
* Specify the bootstrapping and implementation process.
* Accept Governance roles.

## Motivation
### Background

From the outset, the core goal of V3 development has been to be *a significant upgrade to V2*. The end state of V3 should be a fully decentralized protocol that provides the most secure and trusted infrastructure for on-chain capital allocation.


To achieve this Yearn contributors outlined four key requirements for V3 to fulfill:
* Further decentralization at launch and enable progressive decentralization over time.
* Simplify strategy writing.
* Better than Yearn's V1 single vault/strategy offering.
* Better than Yearn's V2 managed vaults.


#### **Vision**:
Yearn V3 attempts to commoditize what Yearn Vaults V2 does. Management and strategy writing becomes easy for anybody to do. Effectively creating an open marketplace of V3 Vaults and strategies that can be operated by any third party, individual or entity without any involvement from Yearn contributors. Our goal is to provide the base infrastructure that all on chain capital allocators use.

The open design of Yearn V3 creates little reason to launch a full fork. Instead encouraging others to build on top of the Yearn stack. We envision the next generation of yield aggregators will be strategists and vault managers in the Yearn marketplace. Integrating their own tokens and using their marketing, risk management, and developer expertise to attract capital.

The high standards Yearn puts on its own vaults has long been the main growth constraint for the protocol. V3 takes these brakes off. Now anyone both within Yearn and outside can build, deploy and manage their own vaults and strategies with any risk profile they desire. While Yearn contributors may certainly choose to continue running V3 versions of our popular very safe single asset vaults or deploying factory vaults. No gate keeping means V3 allows the flexibility to properly experiment and grow the range of strategies and vaults offered.

Perhaps a protocol with a large idle USDC position in their treasury wants to deploy some of those funds to generate returns. They can manage their own vault picking and choosing which strategies from the marketplace are within their risk profile.

This creates opportunities for new and improved Yearn teams to arise and become even more decentralized. For example a yTeam could become a rating agency where vault managers or strategists pay to be reviewed and get rated. Like a very specialized audit firm.

In V3 strategists can now simply write and deploy strategies fully autonomously and people can start using it immediately. Want it to be included in vault? You can apply for a rating and pitch it to vault managers. 

Different vault managers can have different requirements. Perhaps a Yearn vault will require your strategy to be at or above some specific rating threshold. While a 3rd party vault can have entirely different and unique requirements. Above or below the Yearn standard.

With all this commoditization one might wonder about the impact this will have on Yearn earnings. The unique nature and exclusivity of the V2 design generated significant revenues from vault fees that flowed directly to the Yearn treasury. However, in this commoditized future Yearn can not only generate revenue from vault management but also firmly positions our future to be in market technology capture. 

Why spend the incredible amount of time and money it takes to build, audit and launch your own vault system when you can immediately and cheaply leverage the proven and trusted Yearn stack.

We see this to be a positive shift for the Yearn suite of protocols. We will become more resilient to the swings in the crypto markets, and no longer tied to the success of a few other protocols.  Key teams can transition into independent, peripheral and fully autonomous entities. This evolution opens up possibilities for healthy competition and innovation, leading to a reduction in protocol expenses while cementing its market position no matter what direction the market goes in or which specific applications lead the way.



### Definitions

#### Universal Terms
* Vault - A tokenized representation of a yield bearing position. 
* ERC4626 - A standard for a yield bearing vault.

#### Yearn Terms
* V3 Vault - A yearn-branded ERC4626 "meta vault" that is a debt allocator between multiple different strategies. 
* Strategy - A term that V3 uses to refer to any ERC4626 compliant contract that a V3 Vault balances debt between. A strategy can be another Yearn vault but doesn't need to be. It can be anything that implements the same API as an ERC4626 Vault (e.g. sfrxETH).
* V3 Tokenized Strategy - A technical implementation of a Strategy that is also a stand-alone ERC4626 compliant Vault. These are the yield generators in the V3 ecosystem.

### In Depth

**TLDR**: In V3 both Vaults and Strategies are fully stand alone 4626 compliant vaults. The relationship between a V3 Vault and its strategies is entirely changed and are now fully independent. Meaning not only can a vault deploy capital to many strategies. But now, a strategy can accept capital from many different vaults (as well as non-vault sources, like direct deposits from users).

[Vault Spec](https://github.com/yearn/yearn-vaults-v3/blob/master/TECH_SPEC.md)[1]
[Tokenized Strategy Spec](https://github.com/yearn/tokenized-strategy/blob/master/SPECIFICATION.md)[2]

Additional implementation repos include vault-periphery[3], tokenized-strategy-periphery[4], and the ERC4626 router.[5]

## Specification
### Overview
**YIP-75: Launch V3**

### Rationale
The rationale is covered in the Background and Vision: V3 decentralizes vault/strategy development via ERC‑4626 composability, enables permissionless deployment, and expands the ecosystem without requiring Yearn to operate every strategy directly.

### Technical Specification
**1. Relevant Contracts**:

The first release "3.0.0" has been deployed on Ethereum Mainnet, Polygon, Optimism and Avalanche.

Contract Addresses (Constant across all chains):

*Vault BluePrint* (To use EIP-5202) : 0xfC49ca826f8C68c0345410fcA0c7d1e0550d9ee9

*VaultFactory* : 0xD1736eBbdefae37503F3eD8D718b61a494F24c1D

*TokenizedStrategy* : 0xAE69a93945133c00B9985D9361A1cd882d107622

**2. Configuration**:

2.1 Vault Blueprint:
- n/a

2.2 Vault Factory: 
- MAX_FEE_BPS (constant): 50%
- default protocol fee : 20%
- protocol fee recipient : Chain specific V3/Treasury Splitter Contract.
- governance : yChad or equivalent
- Mainnet will have all V3 vaults that have a V2 equivalent have a custom protocol fee set at 40% of the default fee.

2.3 Tokenized Strategy:
- MIN_FEE (constant): 5%
- MAX_FEE (constant) : 50%

### Test Cases
Not applicable.

### Configurable Values
- VaultFactory MAX_FEE_BPS: 50%.
- Default protocol fee: 20% (with 40% default for Mainnet V3 vaults that have V2 equivalents).
- TokenizedStrategy MIN_FEE: 5%.
- TokenizedStrategy MAX_FEE: 50%.
- Governance address: yChad or equivalent (chain-specific).

## References
1. https://github.com/yearn/yearn-vaults-v3/blob/master/TECH_SPEC.md
2. https://github.com/yearn/tokenized-strategy/blob/master/SPECIFICATION.md
3. https://github.com/yearn/vault-periphery
4. https://github.com/yearn/tokenized-strategy-periphery
5. https://github.com/Schlagonia/Yearn-ERC4626-Router

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
