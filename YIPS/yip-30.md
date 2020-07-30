---
yip: 30
title: YFI Inflation Schedule
status: Proposed
author: Substreight (@substreight), DeltaTiger (@deltatigernz), Hannes Graah <hannes@graah.se>, Daryl Lau (@Daryllautk), yfi_whale
discussions-to: https://gov.yearn.finance/t/poll-yfi-inflation-reward-distribution-policy/550
created: 2020-07-28
---

## Simple Summary
Implement an inflation schedule of 20,000 YFI over the next 8 years, with 12,802 distributed in the first 3 years, ending with a trailing tail of 1% inflation.

## Abstract
* Update the YFI mint contract to reflect new inflation schedule.

## Motivation
To create an inflation schedule after the passing of YIP-0. 

**FOR**: Implement an inflation schedule of 20,000 YFI over the next 8 years, with 12,802 distributed in the first 3 years, ending with a trailing tail of 1% inflation.

**AGAINST**: No changes.

## Specification

### Overview
1. Adjust supply schedule to follow [[YFI Inflation Schedule](https://docs.google.com/spreadsheets/d/1yomUGpAWR8svL9RXD-_vL2ArgQPGj1x2XPNKDEuZR9Q/edit?usp=sharing)].
  - Beginning annual inflation: 22.384%
  - Weekly emissions reduction multiplier: 0.9937
  - Week that terminal inflation starts: 416 weeks
  - Fixed % ongoing inflation (tail emission): 1%
2. This model will stay in place until it is stopped or adjusted.

### Rationale

* Liquidity provider yields are maintained at reasonably competitive levels in various YFI price and TVL scenarios (see modeling sheet).
* Lower initial inflation (22%) to keep long-term rewards reasonable.
* 8 year emission schedule to support long-term development.

Reference: [synthetix/contracts/SupplySchedule.sol](https://github.com/Synthetixio/synthetix/blob/master/contracts/SupplySchedule.sol)

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).