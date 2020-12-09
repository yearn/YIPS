---
yip: 48
title: Vaults V2 Design
status: Implemented
author: fubuloubu (@fubuloubu)
discussions-to: https://gov.yearn.finance/t/yip-48-vaults-v2-design/6658
created: 2020-10-06
---

## Summary
This YIP proposes a redesign of the Yearn Vaults system to accommodate several improvements meant to increase the robustness, security, and flexibility of the Vaults moving forwards
 
## Motivation
The current yVault design has made it possible for Yearn to scale to the point it is today. However, due to it's design, it has been difficult to maintain, and is missing a number of features that could improve the risk/return profile of Vaults, and improve their overall security and reliability in the process.

We propose that a refactor of the Vault system to add these features would be an improvement to the overall design, enabling the maintainers of the Yearn codebase to increase their efforts at Quality Assurance and testing for faults, streamline the development of new and innovative strategies (with an improved and standardized API for Strategists to use), and most importantly give the Governance of Yearn the *tools they need* to optimize Vault yields and manage risk of a larger system better.

Improvements for V2 design:
- Allow a Vault to have multiple strategies at the same time
- Streamline the development cycle of new strategies using a standard API
- Streamline the QA/Security process for Vaults, to ensure the highest quality code
- Ensure the Vaults are tested to handle different types of Strategy risk/return/volatility thresholds
- Make it easier and safer for integrators to use Vaults in their projects

## Specification
The Specification for the proposal is being tracked a Gist to better track any changes made.

https://github.com/iearn-finance/yearn-vaults/blob/master/SPECIFICATION.md

**For**: Adopt the proposal

**Against**: Reject the proposal

## Metadata

| Name                | Value                                      |
| ------------------- | ------------------------------------------ |
| Proposed by         | 0x7A1057E6e9093DA9C1D4C1D049609B6889fC4c67 |
| Total for votes     | 1.89k YFI (99.96%                          |
| Total against votes | 0.76  YFI (0.04%)                          |
| Start date          | Oct 6                                      |
| End date            | Oct 9                                      |

_Source: [Snapshot](https://snapshot.page/#/yearn/proposal/QmRKmXuEMaqY38ccvuZREmi6SfMxyhWQMT3mhJ6Cgfeqq9)_

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
