---
yip: <to be assigned>
title: Create Four New Vaults Farming UNI
status: WIP
author: franklin (@franklin501)

created: 2020-10-06
---

<!--You can leave these HTML comments in your merged YIP and delete the visible duplicate text guides, they will not appear and may be helpful to refer to if you edit it again. This is the suggested template for new YIPs. Note that an YIP number will be assigned by an editor. When opening a pull request to submit your YIP, please use an abbreviated title in the filename, `yip-draft_title_abbrev.md`. The title should be 44 characters or less.-->
<!-- This is the suggested template for new YIPs. Note that an YIP number will be assigned by an editor. When opening a pull request to submit your YIP, please use an abbreviated title in the filename, `yip-draft_title_abbrev.md`. The title should be 44 characters or less. -->

## Simple Summary
<!--"If you can't explain it simply, you don't understand it well enough." Simply describe the outcome the proposed changes intends to achieve. This should be non-technical and accessible to a casual community member.-->
<!-- "If you can't explain it simply, you don't understand it well enough." Simply describe the outcome the proposed change intends to achieve. This should be non-technical and accessible to a casual community member. -->
Expand the current vault offering to create four new vaults that would farm UNI. One for each liquidity pool eligible to farm UNI.

## Abstract
<!--A short (~200 word) description of the proposed change, the abstract should clearly describe the proposed change. This is what *will* be done if the YIP is implemented, not *why* it should be done or *how* it will be done. If the YIP proposes deploying a new contract, write, "we propose to deploy a new contract that will do x".-->
Vaults are currently primarily focused on Curve and farming CRV. This proposal would diversify Yearn's revenue source and farm UNI. Four new vaults would be created:

<br>ETH / USDC;
<br>ETH / USDT;
<br>ETH / DAI;
<br>ETH / WBTC

## Motivation
<!--This is the problem statement. This is the *why* of the YIP. It should clearly explain *why* the current state of the protocol is inadequate.  It is critical that you explain *why* the change is needed, if the YIP proposes changing how something is calculated, you must address *why* the current calculation is innaccurate or wrong. This is not the place to describe how the YIP will address the issue!-->
There is a large reliance on Curve for yield generation and this proposal would help shift reliance from one protocol, while also expanding Yearn's yield-farming strategies. 

## Specification
<!--The specification should describe the syntax and semantics of any new feature, there are five sections
1. Overview
2. Rationale
3. Technical Specification
4. Test Cases
5. Configurable Values
-->

### Overview
<!--This is a high level overview of *how* the YIP will solve the problem. The overview should clearly describe how the new feature will be implemented.-->
Enabling new vaults that farm UNI will expand Yearn's yield-farming operations and reduce reliance on Curve as the primary protocol generating revenue for Yearn. 

### Rationale
<!--This is where you explain the reasoning behind how you propose to solve the problem. Why did you propose to implement the change in this way, what were the considerations and trade-offs. The rationale fleshes out what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.-->
By introducing four new vaults that are farming UNI, Yearn can expand its yield-generating activities and reduce reliance on Curve. In addition, farming UNI will bring in additional fees to the Yearn ecosystem. 

### Technical Specification
<!--The technical specification should outline the public API of the changes proposed. That is, changes to any of the interfaces yEarn Finance currently exposes or the creations of new ones.-->
Users would deposit UNI-v2 liquidity tokens into new vaults. These vaults would farm UNI. The UNI would be sold to purchase more of the underlying assets and deposited back into the UNI liquidity pools obtaining more UNI-v2 tokens. The UNI-v2 tokens would be deposited back into the respective vaults. Depositors would have claims over the excess amounts. 0.5% withdrawal fees would be assessed for exiting the vault. 


## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
