---
yip: 79
title: Multisig Compensation and Rotation
author: wavey
discussions-to: https://gov.yearn.fi/t/yip-79-multisig-compensation-and-rotation/14179
status: Proposed
created: 2024-09-26
---

## Simple Summary
Yearn's main multisig, [ychad.eth](https://etherscan.io/address/0xFEB4acf3df3cDEA7399794D0869ef76A6EfAff52)[1], is a 6 of 9 multisig which has key powers within the protocol including ownership over the treasury. For more information, including the current list of signers, please refer to [the docs](https://docs.yearn.fi/developers/security/multisig).[2]

## Abstract
Yearn's main multisig, [ychad.eth](https://etherscan.io/address/0xFEB4acf3df3cDEA7399794D0869ef76A6EfAff52)[1], is a 6 of 9 multisig which has key powers within the protocol including ownership over the treasury. For more information, including the current list of signers, please refer to [the docs](https://docs.yearn.fi/developers/security/multisig).[2]

This proposal aims to:
- outline a YFI compensation plan for signers
- rotate 3 multisig signers

## Motivation
This proposal ensures multisig security and continuity by rotating signers while compensating them for ongoing operational responsibility. It formalizes compensation to recognize signer workload and sets a clear rotation plan.

## Specification
### Overview
### Proposal to rotate multisig signers and provide compensation

Yearn's main multisig, [ychad.eth](https://etherscan.io/address/0xFEB4acf3df3cDEA7399794D0869ef76A6EfAff52), is a 6 of 9 multisig which has key powers within the protocol including ownership over the treasury. For more information, including the current list of signers, please refer to [the docs](https://docs.yearn.fi/developers/security/multisig).

This proposal aims to:
- outline a YFI compensation plan for signers
- rotate 3 multisig signers

### Rationale
The rationale is to keep the multisig both secure and accountable: rotations refresh operational resilience, and compensation aligns incentives for timely execution and oversight.

### Technical Specification
#### Compensation

Currently, ychad.eth signers earn no compensation. If passed, this proposal will:
- retroactively reward all current signers (including outgoing, excluding incoming) 1 YFI each to compensate for past efforts.
- reward all on-going signers (including incoming, excluding outgoing) with 1 YFI.

In summary, all signers who are part of both the past and present state will receive a transfer of 2 YFI. Signers who were part of only past or future state will receive a transfer of 1 YFI.

#### Signer Rotation

A transaction to rotate the first two signers will be queued to execute immediately upon passage of this proposal. Due to prior commitments, the final seat will be rotated at the start of December of this year.

replace the following outgoing signers:
| |                                   |
|--------|------------------------------------------|
| cp0x | `0x74630370197b4c4795bFEeF6645ee14F8cf8997D` |
| milkyklim   | `0x0Cec743b8CE4Ef8802cAc0e5df18a180ed8402A7` |
| **banteg** | `0x7A1057E6e9093DA9C1D4C1D049609B6889fC4c67` |

with the following incoming signers:
| |                                   |
|--------|------------------------------------------|
| cryptoharry (Inverse Finance)  | `0x962228a90eaC69238c7D1F216d80037e61eA9255` |
| michwill (Curve Finance)   | `0xFe45baf0F18c207152A807c1b05926583CFE2e4b` |
| **tapir (Yearn Finance)** | `0x700F1a984C962b447CcDb95c4c2D8074C65098a3` |

*To be executed in December*

### Test Cases
Not applicable.

### Configurable Values
- Compensation: 1 YFI per signer for past service and 1 YFI per ongoing signer (2 YFI for those continuing).
- Multisig threshold: 6 of 9.
- Rotation timing: two signers immediately on passage; final seat at start of December.

## References
1. https://etherscan.io/address/0xFEB4acf3df3cDEA7399794D0869ef76A6EfAff52
2. https://docs.yearn.fi/developers/security/multisig
## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
