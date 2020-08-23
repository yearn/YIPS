---
yip: <to be assigned>
title: add `trade()` functionality to the Y pool
status: WIP
author: 
discussions-to: <Create a new thread on https://gov.yearn.finance/ and drop the link here>

created: 2020-08-23
requires: None
implementation: WIP
---

## Simple Summary

A `trade()` function is added to the Y pool such that traders can supply a certain stablecoin X and receive another stablecoin Y according to a quote by stablecoin-optimized CFAMM curve. Interacting with `trade()` triggers the necessary re-balancing mechanism as usual. The net effect on the pool yield-optimizing allocation is equivelant to a `deposit(X)` followed immediately by a `withdraw(Y)`. Y pool depositors opt-in to participate and be eligible for trading fees. 


## Abstract


A short (~200 word) description of the proposed change, the abstract should clearly describe the proposed change. This is what *will* be done if the YIP is implemented, not *why* it should be done or *how* it will be done. If the YIP proposes deploying a new contract, write, "we propose to deploy a new contract that will do x".

A `public trade(input X, min_output Y)` function is added to the Y facility. Anyone can call it to supply `X` amounts of one stablecoin and receive at least `Y` amount of another stablecoin. The quote provided is according to a stablecoin-optimized CFAMM curve. If the trade is successful, the Y pool is rebalanced if necessary. The effect on the pool yield-optimizing allocation is equivelant to having a batched transaction of `deposite(X) && withdraw(Y)`.


## Motivation

- Remove intermediaries between Y pool LPs and the trading fees they earn should they opt-in in the trading facility.
- Reduce extra-Y-protocol governance risks when a significant chunk of 
- Y depositors who are also interested in trading fees should not have to absorb governance risk from this choice other than YFI governance risk.
- There is added risk but no added value to having a seperate govenance controlling the trading facility. The incentives are aligned between YFI governors who are not participating in the trading facility and Y depositors who are, because the funds accessable by CFAMM still earns yield in the same manner than Y funds opting out of the trading facility are. 
- 

## Specification

### Overview

### Rationale

- Governance risk minimization: Y depositors should not absorb more governance risk more than YFI governance.
- UI/UX: opting-in to the trading facility is just a check box, not a whole dedicated frontend which adds confusion
- 

### Technical Specification

### Test Cases

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
