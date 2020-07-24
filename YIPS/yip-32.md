---
yip: 32
title: Remove YFI burning
status: Proposed
author: Sunil Srivatsa (@alphastorm)
discussions-to: https://gov.yearn.finance/t/yip-32-remove-yfi-burning/1907
created: 2020-08-01
---

## Simple Summary
Remove YFI burning from the protocol.

## Abstract
YFI represents a claim on yEarn protocol fees. To claim fees, YFI can either be burned or staked in the governance pool.

This YIP is to decide whether or not to keep the burning mechanism.

## Motivation
It makes no sense to burn because the price of YFI will always be higher than the claimable fee value. This is because YFI represents current assets in the fee pool plus future expected cashflows. Staking is just obviously better.

**FOR**: Remove YFI burning from the protocol.

**AGAINST**: No change (start burning YFI for fees).

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
