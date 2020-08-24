---
yip: <to be assigned>
title: add `trade()` functionality to the Y pool
status: WIP
author: Ali Atiia (@aliatiia)
discussions-to: https://gov.yearn.finance/t/proposal-bolt-a-cfamm-facility-to-the-y-pool/3434

created: 2020-08-23
requires: None
implementation: WIP
---

## Simple Summary

A `trade()` function is added to the Y pool such that traders can supply a certain stablecoin X and receive another stablecoin Y according to a quote by stablecoin-optimized CFAMM curve. Interacting with `trade()` triggers the necessary re-balancing mechanism as usual. The net effect on the pool yield-optimizing allocation is equivelant to a `deposit(X)` followed immediately by a `withdraw(Y)`. Y pool depositors opt-in to participate and be eligible for trading fees. 


## Abstract

A `public trade(input X, min_output Y)` function is added to the Y facility. Anyone can call it to supply `X` amounts of one stablecoin and receive at least `Y` amount of another stablecoin. The quote provided is according to a stablecoin-optimized CFAMM curve. If the trade is successful, the Y pool is rebalanced if necessary. The effect on the pool yield-optimizing allocation is equivelant to having a batched transaction of `deposite(X) && withdraw(Y)`.


## Motivation

- Remove intermediaries between Y pool LPs and the trading fees they earn should they opt-in in the trading facility.
- Reduce extra-Y-protocol governance risks
- Y depositors who are also interested in trading fees should not have to absorb governance risk from this choice other than YFI governance risk.
- The incentives are aligned between YFI governors who are not participating in the trading facility and Y depositors who are, because the funds accessable by CFAMM still earns yield in the same manner than Y funds opting out of the trading facility are. 
- 

## Specification

### Overview

### Rationale

- Governance risk minimization: Y depositors should not absorb more governance risk than necessary. YFI governance suffices.
- Better UI/UX: opting-in to the trading facility is just a check box, not a whole dedicated frontend which adds confusion.
- Sustainability and incentive alignments: the fruits of network effects of the trading facilities is kept within the YFI ecosystem
### Technical Specification

### Test Cases

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
