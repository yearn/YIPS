---
yip: 47
title: Release Fee Rewards
status: Implemented
author: milkyklim (@milkyklim)
discussions-to: https://gov.yearn.finance/t/yip-47-release-fee-rewards/6013
created: 2020-09-21
---

**UPD:** Set `breaker` to `true` indefinitely as per [YIP: Release fee rewards](https://gov.yearn.finance/t/yip-release-fee-rewards/6013/2).

## Summary

Allow people to claim their rewards right now without any on-going voting.

## Abstract

Multisig will set `breaker` to `true` in the governance [contract](https://etherscan.io/address/0xBa37B002AbaFDd8E89a1995dA52740bbC013D992#writeContract). This will allow people to claim rewards instantly.

## Motivation

With current ethereum gas [prices](https://explore.duneanalytics.com/embed/query/6245/visualization/12389?api_key=L5Ck5TNvSPqjtK1ddZhaQjuyDGVuboeaC6AKz41q) governance migrated to snapshot off-chain voting/signaling. While voting and saving on gas fees voters are unable to claim fee rewards acquired by the protocol.

## Specification

No new code will be deployed. If this proposal passes multisig will set `breaker` to `true` in the governance [contract](https://etherscan.io/address/0xBa37B002AbaFDd8E89a1995dA52740bbC013D992#writeContract).

**For**: Set `breaker` to `true`.

**Against**: Keep things as they are now.

## Metadata

| Name                | Value                                      |
| ------------------- | ------------------------------------------ |
| Proposed by         | 0x0Cec743b8CE4Ef8802cAc0e5df18a180ed8402A7 |
| Total for votes     | 1.17k YFI (94.78%)                         |
| Total against votes | 64.4 YFI (5.22%)                           |
| Start date          | Sep 20                                     |
| End date            | Sep 23                                     |

_Source: [Snapshot](https://snapshot.page/#/yearn/proposal/QmXudfEC9Lo9cv7j89h98WaSsVVMMWa1KKRyN4thgcEhrh)_

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
