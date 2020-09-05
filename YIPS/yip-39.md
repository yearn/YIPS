---
yip: 39
title: Add Curve sBTC Pool LP-Tokens yVault
status: Implemented
author: uhmpeps (@az)
discussions-to: https://gov.yearn.finance/t/proposal-add-curve-sbtc-pool-lp-tokens-yvault/3251

created: 08/23/2020
---

<!--You can leave these HTML comments in your merged SIP and delete the visible duplicate text guides, they will not appear and may be helpful to refer to if you edit it again. This is the suggested template for new SIPs. Note that an SIP number will be assigned by an editor. When opening a pull request to submit your SIP, please use an abbreviated title in the filename, `sip-draft_title_abbrev.md`. The title should be 44 characters or less.-->

## Simple Summary
<!--"If you can't explain it simply, you don't understand it well enough." Simply describe the outcome the proposed changes intends to achieve. This should be non-technical and accessible to a casual community member.-->
Capture up to $214b in AUM from BTC holders who want to passively grow their BTC holdings by using some voting power to increase sBTC pool CRV returns and create a Vault for sBTC Curve Pool LP-token holders who deposit renBTC / wBTC / sBTC in Curve Pool 6. This can generate significant goodwill from Bitcoin holders who may not be aware of other use cases for their holdings currently.

It’s the Curve sBTC pool which accepts renBTC / wBTC / sBTC which are all equally acceptable and gives the most potential rewards.
We only need to accept the LP-token which is a single token type given to depositors of any type of wrapped BTC.

## Abstract
<!--A short (~200 word) description of the proposed change, the abstract should clearly describe the proposed change. This is what *will* be done if the SIP is implemented, not *why* it should be done or *how* it will be done. If the SIP proposes deploying a new contract, write, "we propose to deploy a new contract that will do x".-->
Create a Grow Vault for sBTC Curve Pool LP-token depositors which functions almost identically to the yCRV and yYFI vault. Harvest CRV, sell it for more LP-tokens or renBTC which is then re-deposited to create, distribute and compound LP-token growth.

## Motivation
<!--This is the problem statement. This is the *why* of the SIP. It should clearly explain *why* the current state of the protocol is inadequate.  It is critical that you explain *why* the change is needed, if the SIP proposes changing how something is calculated, you must address *why* the current calculation is innaccurate or wrong. This is not the place to describe how the SIP will address the issue!-->
First big mover advantage. There is room to generate significant goodwill from bitcoin holders ($214b in potential AUM) by using our voting power to kick % rewards increase toward the sBTC pool, and to create the first fully passive mechanism for BTC holders to increase their Bitcoin holdings. Right now only the most confident BTC holders are depositing and recycling / farming CRV. This can become a black hole for BTC deposits into Curve via renBTC and LP tokens into yVault for passive returns and governance fees.

## Specification
<!--The specification should describe the syntax and semantics of any new feature, there are five sections
1. Overview
2. Rationale
3. Technical Specification
4. Test Cases
5. Configurable Values
-->

[1]

* Add a table row under the Grow Vault product, for LP-token holders who deposited funds into the Curve sBTC Pool named appropriately (don’t know what the LP token is called atm)
* When user deposits Curve sBTC LP-token, system stakes the LP-token to Curve DAO and farms CRV
* Upon receipt and sale of CRV on market, system buys either more LP-token if liquidity/pools are available, or buys renBTC or sBTC
* xBTC is then deposited back to the Curve sBTC pool, LP-tokens generated, shown in table for depositors as gains, and meanwhile LP-tokens are cycled back into Curve DAO to compound CRV generation

[2]

* Use some voting power to increase CRV return generation for BTC depositors to 50-70% to make it highly compelling for BTC holders
* Ensure the new yVault is communicated to the appropriate audiences as a viable alternative to holding a non functional pet rock with no other purpose currently.

**For:** Add Vault for sBTC Curve Pool.

**Against:** No change.
