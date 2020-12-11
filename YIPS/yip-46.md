---
yip: 46
title: Upgrade Treasury Vault to solve gas subsidy, gitcoin and more
status: Approved
author: banteg (@banteg)
discussions-to: https://gov.yearn.finance/t/yip-46-upgrade-treasury-vault-to-solve-gas-subsidy-gitcoin-and-more/4732
created: 2020-09-04
---

## Summary

This proposal bundles a few improvements together which have compounding effects. It will solve for [gas subsidy](https://gov.yearn.finance/t/gas-costs-are-too-damn-high/4655), [gitcoin grants](https://gov.yearn.finance/t/direct-of-rewards-towards-ethereum-public-goods-funding/3699), inability to convert other Curve tokens into rewards for governance stakers.

## Abstract

Add split functionality to TreasuryVault which can send the rewards to multiple destinations before sending them to governance staking contract. Add ability to withdraw from Curve pools. Add ability to trade using Uniswap.

## Motivation

There is a very good [competing proposal](https://gov.yearn.finance/t/proposal-change-vault-harvest-function-to-reward-function-caller/4726) which solves for gas refunds by modifying `harvest()` function. But here is some rationale for using TreasuryVault instead:

1. Putting this in `harvest()` doesn't refund on failed txs, which can eat up $500 by the moment it fails
2. Requires redeploying and migrating all strategies, which can't be done easily for the strategies yDAI and yWETH vaults are currently positioned in.
3. Treasury contract needs upgrading anyway, I was working on a converter and reward distribution bot and was stuck with OneSplit not being smart enough to unwrap Curve LP tokens.
4. We'll be able to solve converting other assets finally and distribute the rewards accumulated from vaults other than yUSD.
5. We can bundle this with gitcoin proposal, which is time-sensitive, since the next round starts on September 15th.

## Specification

1. Develop and deploy a TreasuryVaultV2 contract with these additional features:

   - Ability to whitelist additional [CurveDeposit](https://www.curve.fi/contracts) contracts when more pools are created.
   - Unwrap into underlying Curve LP coins or a single coin (CurveDeposit has us covered here).
   - Trade via Uniswap in addition to OneSplit, this helps immensely with testing and optimizing the bot which does the trading.
   - [Disperse](https://disperse.app)-like split functionality which can send different amounts to multiple recipients.
   - The split functionality should also call `notifyRewardAmount` when it sends rewards to `ygov`.

2. This proposal will require some additional work for gas accounting, which can be delegated to a bot.

### Implementers

@andrecronje

### Urgency

Given the gas costs are eating through our budget at $25k/day rate, I propose to have an expedited vote for this with a 1-day duration. We should have the implementation ready shortly after.

### Voting

**For**: Implement the proposal

**Against**: Do not implement the proposal

## Metadata

| Name                | Value                                      |
| ------------------- | ------------------------------------------ |
| Proposed by         | 0x7A1057E6e9093DA9C1D4C1D049609B6889fC4c67 |
| Total for votes     | 1.39k YFI (100%)                           |
| Total against votes | 0.00 YFI (0.00%)                           |
| Start date          | Sep 4                                      |
| End date            | Sep 5                                      |

_Source: [Snapshot](https://yearn.snapshot.page/#/yearn/proposal/QmaWoU9y6P1P7FTc4dH8gwoorwdMXM2oZbGLGRePM3MfUV)_

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
