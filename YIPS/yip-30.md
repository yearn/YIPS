---
yip: 30
title: YFI Inflation Schedule
status: Proposed
author: Substreight (@substreight), DeltaTiger (@deltatigernz), Hannes Graah, Daryl Lau (@Daryllautk), yfi_whale
discussions-to: TODO
created: 2020-07-28
---

## Simple Summary
Implement an inflation schedule of 20,000 YFI over the next 8 years, with 12,802 distributed in the first 3 years, ending with a trailing tail of 1% inflation.

## Abstract
1. Update the YFI mint contract to reflect the new inflation schedule.
2. Allocate 75% of YFI emission to LP rewards.
3. Allocate 25% of YFI emission to Multisig // DAO for security, development, and future incentives.

## Motivation
To create a clear inflation schedule which reflects the long-term best interest of the community, allowing some flexibility in the adjustment of reward schemes. 

Prior proposals are potentially too conservative and/or not specific enough. This proposal takes into account the perspectives of various stakeholders and new LPs while providing a clear inflation schedule and endpoint. 

**FOR**: Implement an inflation schedule of 20,000 YFI over the next 8 years, with 12,802 distributed in the first 3 years, ending with a trailing tail of 1% inflation.

**AGAINST**: No changes.

## Specification

### Overview
1. Inflation schedule to follow [[YFI Inflation Schedule](https://docs.google.com/spreadsheets/d/1yomUGpAWR8svL9RXD-_vL2ArgQPGj1x2XPNKDEuZR9Q/edit?usp=sharing)].
  - Beginning annual inflation: 22.384%
  - Weekly emissions reduction multiplier: 0.9937
  - Week that terminal inflation starts: 416
  - Fixed % ongoing inflation (tail emission): 1%
2. 75% of future YFI emissions (15k YFI) designated to LP rewards.
3. 25% of future YFI emissions (5k YFI) designated to Multisig//DAO.

### Rationale

* Liquidity provider yields are maintained at reasonably competitive levels in various YFI price and TVL scenarios (see modeling sheet).
* Lower initial inflation (22%) to keep long-term rewards reasonable.
* 8 year emission schedule to support long-term development.

Reference: [synthetix/contracts/SupplySchedule.sol](https://github.com/Synthetixio/synthetix/blob/master/contracts/SupplySchedule.sol)

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
