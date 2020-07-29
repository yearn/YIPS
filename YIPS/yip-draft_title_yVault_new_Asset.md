---
yip: <to be assigned>
title: Add LINK as the first volatile asset as collateral for delegated yVaults
status: WIP
author: franklin (@franklin501) 
discussions-to: https://gov.yearn.finance/t/add-link-as-the-first-asset-for-the-upcoming-delegated-yvaults-release/847

created: 2020-07-28
requires (*optional): <YIP number(s)>
implementation (*optional): <Added if YIP passes>
---
  
<!--You can leave these HTML comments in your merged YIP and delete the visible duplicate text guides, they will not appear and may be helpful to refer to if you edit it again. This is the suggested template for new YIPs. Note that an YIP number will be assigned by an editor. When opening a pull request to submit your YIP, please use an abbreviated title in the filename, `yip-draft_title_abbrev.md`. The title should be 44 characters or less.-->
## Simple Summary
<!--"If you can't explain it simply, you don't understand it well enough." Simply describe the outcome the proposed changes intends to achieve. This should be non-technical and accessible to a casual community member.-->
Add Chainlink (LINK) as the first volatile asset to be used as collateral in delegated yVaults.

## Abstract
<!--A short (~200 word) description of the proposed change, the abstract should clearly describe the proposed change. This is what *will* be done if the YIP is implemented, not *why* it should be done or *how* it will be done. If the YIP proposes deploying a new contract, write, "we propose to deploy a new contract that will do x".-->
Add either Chainlink (LINK) or Ether (ETH) as the first volatile asset to be used as collateral in delegated yVaults. 

## Motivation
<!--This is the problem statement. This is the *why* of the YIP. It should clearly explain *why* the current state of the protocol is inadequate.  It is critical that you explain *why* the change is needed, if the YIP proposes changing how something is calculated, you must address *why* the current calculation is innaccurate or wrong. This is not the place to describe how the YIP will address the issue!-->
Delegated yVaults has initially launched with only USDC as collateral. Additional assets are necessary in order to generate more revenue to the protocol and grow the ecosystem. This proposal is to determine the first volatile asset to be used as collateral, which will be tested in trials before other volatile assets are added. A preliminary vote was conducted at https://yearn.gov.finance and the top two choices to add as the first volatile asset were LINK and ETH. 

**FOR**: Add LINK as the first volatile asset to be used in delegated yVaults.
**AGAINST**: Add ETH as the first asset to be be used in delegated yVaults. 

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
Adding LINK as a collateral option to delegated yVaults will enable LINK holders to deposit tokens to the vault, which will increase the total value locked (TVL) and generate more fees for the protocol. 

### Rationale
<!--This is where you explain the reasoning behind how you propose to solve the problem. Why did you propose to implement the change in this way, what were the considerations and trade-offs. The rationale fleshes out what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.-->
Chainlink is among the highest valued and most liquid ERC-20 tokens. There is a significant number of tokens and thus liquidity idle, which could be deposited for delegated yVaults. LINK’s high market capitalization makes it well suited to be the first delegated yVault volatile asset as it will likely contribute to the most fees that will be accrued the protocol. 

Chainlink also has one of the strongest communities in crypto and successful initial trials of delegated yVaults will likely encourage larger token holders to join the ecosystem adding even more fees. Large deposits of LINK as collateral will significantly increase total value locked (TVL) in yVaults, compared to other token communities that are not as immersed in DeFi. 

### Technical Specification
<!--The technical specification should outline the public API of the changes proposed. That is, changes to any of the interfaces yEarn Finance currently exposes or the creations of new ones.-->

### Test Cases
<!--Test cases for an implementation are mandatory for YIPs but can be included with the implementation..-->

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
