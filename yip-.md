---
yip: 
title: Add yRenBTC Vault Strategy 1 - StrategyCreamRENBTC
status: Proposed
author: Azeem (@zu-ctrl)
discussions-to: https://gov.yearn.finance/t/proposal-yrenbtc-delegated-vault/3470
smart-contract: https://github.com/zu-ctrl/yfi-str-pub/blob/master/StrategyCreamRENBTC.sol
created: 08/25/2020
---
<!--You can leave these HTML comments in your merged SIP and delete the visible duplicate text guides, they will not appear and may be helpful to refer to if you edit it again. This is the suggested template for new SIPs. Note that an SIP number will be assigned by an editor. When opening a pull request to submit your SIP, please use an abbreviated title in the filename, `sip-draft_title_abbrev.md`. The title should be 44 characters or less.-->

## Simple Summary
<!--"If you can't explain it simply, you don't understand it well enough." Simply describe the outcome the proposed changes intends to achieve. This should be non-technical and accessible to a casual community member.-->
wBTC has pretty good growth rates as seen on defipulse but as a custodial solution is hampered by trust-based systems which BTC holders do not by and large feel comfortable with.

RenBTC is a tokenized representation of BTC on the Ethereum blockchain. It is an ERC20, and backed 1:1 with real BTC locked in RenVM, a decentralized custodian. It is redeemable at any time for real BTC.

When Curve created an opportunity for RenBTC to generate returns, the RenVM TVL growth chart exploded. This is a clear signal that when the right solution is available, there is a LOT of BTC waiting on the sidelines to jump into farming yield on ETH. Let’s be there for them.

## Abstract
<!--A short (~200 word) description of the proposed change, the abstract should clearly describe the proposed change. This is what *will* be done if the SIP is implemented, not *why* it should be done or *how* it will be done. If the SIP proposes deploying a new contract, write, "we propose to deploy a new contract that will do x".-->
Strategy options / sequence:
* Strategy 1: Accept RenBTC deposits immediately without RenVM bridge, start farming CREAM the same way as yYFI Vault, and deliver returns for depositors as RenBTC
* Strategy 2: Accept RenBTC deposits immediately without RenVM bridge, start farming CRV the same way as yCRV Vault, and deliver returns for depositors as RenBTC
* Strategy 3: Soon as sensible, add RenVM for Direct BTC Deposit as an option on Product Pages
* Strategy 4: When MakerDAO launches RenBTC collateral, allow users to deposit BTC directly via RenVM Bridge on our site like Curve does for deposits (can also accept RenBTC if user already has it), we give user yRenBTC, turn their BTC into RenBTC, Create a CDP, manage collateral and use our vaults to generate yield, which is used to buy RenBTC on the market and deliver returns to depositors as RenBTC. This allows a user to deposit BTC and increase their BTC stack while also generating significant buy pressure on the market for BTC.

## Motivation
<!--This is the problem statement. This is the *why* of the SIP. It should clearly explain *why* the current state of the protocol is inadequate.  It is critical that you explain *why* the change is needed, if the SIP proposes changing how something is calculated, you must address *why* the current calculation is innaccurate or wrong. This is not the place to describe how the SIP will address the issue!-->
Capture up to $214b in AUM from BTC holders who want to passively grow their BTC holdings to gain a big first mover advantage. There is room to generate significant goodwill from bitcoin holders by creating the first truly passive method to generate returns in BTC using the best strategy available at any time.

## Specification
<!--The specification should describe the syntax and semantics of any new feature, there are five sections-->
> Strategy 1:
* Add a new Vault row in Table for yRenBTC Vault
* User deposits RenBTC start farming CREAM the same way as yYFI Vault, and deliver returns for depositors as RenBTC

> Strategy 2 (switch between 1 and 2 depending on best returns):
* Add a new Vault row in Table for yRenBTC Vault or recycle row from Strategy 1
* User deposits RenBTC start farming CRV the same way as yCRV Vault, and deliver returns for depositors as RenBTC
* Consider dedicating a portion of CRV rewards weekly to restake to veCRV to maximize multiple rewards

> Strategy 3:
* Figure out how to create a RenVM bridge that works with our systems to accept BTC, we give user yRenBTC, turn their BTC into RenBTC, and manage appropriately.
* Add this as an option to each UX touch point which accepts RenBTC. 

> Strategy 4: 
* Add a new Vault row in Table for yRenBTC Vault or recycle from S1/2
* Create a RenVM Bridge deposit form in Vault Product similar to how Curvefi does it [here](https://www.curve.fi/ren/deposit) (click X on BTC icon) - this can be added as a toggle on the usual RenBTC deposit form, or it could be a separate deposit form just for BTC so holders don't get confused and think RenBTC is some alt/fork... we can explain correctly on the product page for it. 
* User deposits BTC (or RenBTC if they already have it), we give user yRenBTC, turn their BTC into RenBTC, Create a CDP, manage collateral and use our vaults to generate yield through whatever method using DAI, which is used to buy RenBTC on the market and deliver returns to depositors as RenBTC. Or directly use RenBTC to farm CRV. 

Zai in Discord mentioned: 
> I know nobody asked, but #4 is amazing. There are intangible morale benefits to this vault continuously adding prime quality collateral into a Maker CDP, and pumping new Dai into the system. Yearn would be hailed as heroes of DeFi.

**For:** Yes! Add RenBTC Vaults.

**Against:** No change.

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).

