---
yip: 42
title: Add RenBTC to yVaults
status: Rejected
author: Azeem (@zu-ctrl)
discussions-to: https://gov.yearn.finance/t/proposal-yrenbtc-delegated-vault/3470
implementation: https://github.com/zu-ctrl/yfi-str-pub/blob/master/StrategyCreamRENBTC.sol
created: 08/26/2020
---
<!--You can leave these HTML comments in your merged SIP and delete the visible duplicate text guides, they will not appear and may be helpful to refer to if you edit it again. This is the suggested template for new SIPs. Note that an SIP number will be assigned by an editor. When opening a pull request to submit your SIP, please use an abbreviated title in the filename, `sip-draft_title_abbrev.md`. The title should be 44 characters or less.-->

## Simple Summary
<!--"If you can't explain it simply, you don't understand it well enough." Simply describe the outcome the proposed changes intends to achieve. This should be non-technical and accessible to a casual community member.-->
Add RenBTC as a volatile asset to be used as collateral in delegated yVaults.

## Abstract
<!--A short (~200 word) description of the proposed change, the abstract should clearly describe the proposed change. This is what *will* be done if the SIP is implemented, not *why* it should be done or *how* it will be done. If the SIP proposes deploying a new contract, write, "we propose to deploy a new contract that will do x".-->

Add RenBTC as a volatile asset to be used as collateral in delegated yVaults.

## Motivation
<!--This is the problem statement. This is the *why* of the SIP. It should clearly explain *why* the current state of the protocol is inadequate.  It is critical that you explain *why* the change is needed, if the SIP proposes changing how something is calculated, you must address *why* the current calculation is innaccurate or wrong. This is not the place to describe how the SIP will address the issue!-->
wBTC has pretty good growth rates as seen on DeFi Pulse but as a custodial solution is hampered by trust-based systems which BTC holders do not by and large feel comfortable with.

RenBTC is a tokenized representation of BTC on the Ethereum blockchain. It is an ERC20, and backed 1:1 with real BTC locked in RenVM, a decentralized custodian. It is redeemable at any time for real BTC.

When Curve created an opportunity for RenBTC to generate returns, the RenVM TVL growth chart exploded. This is a clear signal that when the right solution is available, there is a LOT of BTC waiting on the sidelines to jump into farming yield on ETH. Let’s be there for them.

Refer to thread with an overwhelming majority FOR the BTC strategic focus. This is a vote to approve the current Strategy Smart contract to go live and start generating returns for RenBTC depositors without forcing them to figure out Curve deposits. 

## Specification
<!--The specification should describe the syntax and semantics of any new feature, there are five sections-->
The strategy linked to above models the current yYFI yVault strategy of farming CREAM and generating returns in more CREAM. We will require a new row in the yVault to accept RenBTC deposits. 

> Strategy 1:
* Add a new Vault row in Table for yRenBTC Vault
* User deposits RenBTC start farming CREAM the same way as yYFI Vault, and deliver returns for depositors as RenBTC.

**For:** Yes! Add yRenBTC Vault Strategy 1 - StrategyCreamRENBTC

**Against:** No change.

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).

