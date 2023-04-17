---
yip: 71
title: Activate veYFI
author: darkghosty, flashfish, jiji, saltyfacu
discussions-to: https://gov.yearn.finance/t/proposal-activate-veyfi/12783
status: Implemented
created: 2022-11-25
---

## Summary

Replace YFI voting with vote-escrowed YFI (veYFI) voting for all future governance proposals.  

### Status

**Discussion**
This proposal is currently in the discussion phase. As per our voting rules outlined in YIP-55, it will be in discussion for at least 3 days with a non-binding forum poll to gauge sentiment before it can be assigned a YIP number and move to Snapshot for a binding vote.


## Abstract

**If adopted**, this proposal seeks to:
* Replace YFI with veYFI as the voting token in Governance
* Adopt a 2 week long moratorium on new YIPs where no proposals will be voted on   

## Background

This proposal is the first step in the implementation of YIP-65: Evolving YFI Tokenomics[[1]](#References). YFI is time-locked up to 4 years where a longer lock increases the relative weight in relation to other locked tokens. It is strongly recommended that the reader first familiarize themselves with the concepts of YIP-65 in order to better understand this proposal.

### Out of scope

The following topics were intentionally not covered by this proposal:
* Yearn Tokenomics
* Gauges
* Rewards
* On-chain voting
 
## Motivation

This implements parts of what was was adopted by YFI voters in YIP-65, namely locking YFI into veYFI, managing one's lock, and using it to vote in governance. There are no YFI rewards or gauges yet. There is no advantage to locking early.

### Future possibilities
* Deploy additional components of YIP-65
* Transition to on-chain voting and governance

### Risks

* Governance attacks, mitigated by a moratorium on new YIPs being accepted
* Smart contract risk in the veYFI contracts, which have been mitigated through security reviews by Statemind, yAcademy, and ChainSecurity[[2]](#References).

### Alternatives considered

None

## Specification

1. veYFI is implemented as per the deployed contract[[3]](#References), from the veYFI github repo[[4]](#References).
2. **DO NOT INTERACT WITH THE CONTRACT TO LOCK YFI** until this proposal passes. There is **NO USE** for locking YFI until this time. There is **NO UPSIDE** in locking early. There are **NO REWARDS** at this point.
3. It's a typical veCRV style locking design:
   * 1 lock per address
   * Min lock: 1 week, max lock 208 weeks (4y)
   * Linear decay
   * Extendable lock duration
4. Immediately upon the passing of this YIP, **all subsequent YIPs are voted on using veYFI**.
5. Voting continues to be done using Snapshot. 
6. To reduce the risk of governance attacks by allowing enough YFI holders to lock so as not to give small YFI balances outsize influence over the protocol, a **2 week moratorium** on YIPs are passed. Any YIP proposal submitted in this period will only be considered for voting 2 weeks after the passing of this YIP.
7. Contributor YFI is migrated into veYFI as per YIP-66: Streamlining contributor compensation[[5]](#References).  
8. veYFI voters may replace this voting mechanism in the future with some other design, by submitting a YIP and voting it through.

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).

## References

1. https://gov.yearn.finance/t/yip-65-evolving-yfi-tokenomics/11994
1. https://github.com/yearn/yearn-security/pull/70/files
1. https://etherscan.io/address/0x90c1f9220d90d3966fbee24045edd73e1d588ad5#code
1. https://github.com/yearn/veYFI/commit/bb9d8ac9dd90a9a9772b9663ce4fa232fda7bce2 
1. https://gov.yearn.finance/t/yip-66-streamlining-contributor-compensation/12247

## Information

_Source: [Snapshot](https://snapshot.org/#/ybaby.eth/proposal/0xc50b60f712adb8568f10f565fc467e8c5d8fe1f4920683696f81c7920397942a)_

| Name          | Value                                                                           |
| ------------- | ------------------------------------------------------------------------------- |
| Snapshot Space| [ybaby.eth](https://snapshot.org/#/ybaby.eth)                                   |
| Strategie(s)  | YFI, delegation                                                                 |
| Author        | wentokyo.eth                                                                    |
| IPFS          | https://snapshot.mypinata.cloud/ipfs/bafkreihcrsciiqm3fhr2kehbtqfjwk7fykepgfv2xgb6rjwwbxm2orwxfq |
| Voting System | Single choice voting                                                            |
| Start date    | Nov 25, 2022                                                                    |
| End date      | Nov 30, 2022                                                                    |
| Snapshot      | https://etherscan.io/block/16048538                                             |

## Results

| Result  | Value             |
| ------  | ----------------- |
| Yes     | 1300 YFI (99.78%) |
| No      | 2.7 YFI (0.21%)   |
| Abstain | 0.025 YFI (0%)    |