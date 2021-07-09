---
yip: 56
title: BABY:\ Buyback and Build Yearn 
status: Approved
author: @banteg, @lex_node, @lehnberg, @milkyklim, @tracheopteryx, @RyanWatkins
discussions-to: https://gov.yearn.finance/t/yip-56-buyback-and-build/8929/114
created: 2021-01-16
---

## Authors
@banteg, @lex_node, @lehnberg, @milkyklim, @RyanWatkins, @tracheopteryx

## Summary
Use YFI staking rewards to buy back YFI on the open market. Use bought back YFI for contributor rewards and other Yearn initiatives. Retire the YFI governance vault as it no longer has a use, opening up for it to be replaced in the future with a regular vault. Make it possible to participate in Governance even if one's YFI is being used elsewhere.

## Abstract

### **If adopted**, this proposal seeks to:

1. Replace YFI staking rewards with YFI buybacks, until further notice.
1. Enable YFI that's actively being used in ways that bring benefit to Yearn to participate in Governance.
1. Retire the YFI governance vault (yGov).

### This **benefits Yearn** as a whole by:

1. Simplifying Treasury design and operation.
1. Simplifying YFI token mechanics to equally align interests across Yearn stakeholders.
1. Builds up a treasury of YFI that can be deployed through Governance for various uses.

### This **benefits YFI holders** in particular by:

1. Removing the need to stake YFI to enjoy rewards; in contrast to staking (which only benefits stakers), buybacks should benefit every YFI holder.
1. Potentially making gains more tax efficient as capital appreciation through buybacks could be taxed less than dividend income through staking rewards.
1. Allowing participation in YFI Governance even whilst the YFI tokens are utilized elsewhere, for example providing liquidity in SushiSwap.

## Motivation

### Previous proposals

#### This proposal comes on the back of previously made proposals and YIPs:

- The adoption of YIP-54[1] formalized an Operations Fund and allowed for discretionary YFI buybacks.
- @RyanWatkins proposed a rethink of Yearn’s capital allocation strategy.[2] Arguing for protocol rewards to be used to buy back YFI rather than to reward YFI stakers, distributing protocol income as dividends would be a suboptimal capital allocation strategy given Yearn’s stage of maturity. Instead, the proposal claimed it would be more optimal to use income to drive growth and asset appreciation instead.
- @dudesahn called for the existing Governance vault and strategy to be replaced with more conventional investment strategy.[3] Utilizing MakerDAO to mint DAI, this would be used for liquidity mining. One part of the returns would be rewarded to stakers, and the other would be used to fund Yearn's Bug Bounty program and yAcademy.
- Joel Monegro (Placeholder VC) recently published the essay “Stop Burning Tokens – Buyback And Make Instead”[4] where he suggested that protocols should buy back and reissue tokens to incentivize growth rather than buying back and burning tokens to return value to token holders. This buyback strategy could be especially well suited for Yearn as the YFI supply is capped at 30,000, meaning that the initial conditions for Yearn’s wealth distribution have been set, and no YFI can be further issued to incentivize growth. Such a “Buyback and Make” strategy could allow Yearn to receive the benefits of YFI inflation without any inflation.

## Rationale

![](https://i.imgur.com/4wYQAXb.png)

### Replace staking rewards with buybacks

- More suitable at this stage in the lifecycle. It is unconventional to pay out returns in the form of staking rewards this early in a project's lifecycle. Typically this would happen at a stage where funds no longer can be allocated efficiently.
- Better aligns with YFI's use case. YFI is primarily intended to be used for the governance of Yearn. Token mechanics should cater to those who take interest in the protocol and wish to actively participate in its improvement, over those looking to passively collect staking income.
- Potentially more tax-efficient for YFI holders. The gains on YFI staking may be treated as ordinary income. In contrast, a buyback program enables growth in YFI while YFI holders should only be taxed on a capital gains basis for a sale. Results may vary by jurisdiction and this does not constitute tax advice; consult your own tax advisor.
- Recycles YFI that can be spent through Governance. The resulting accumulation of YFI in the Treasury could enable future governance proposals on the use of this YFI for the further benefit of Yearn.

### Widen YFI accepted for Governance voting

- Acknowledge more uses of YFI for the benefit of Yearn. There are other ways than holding YFI in your wallet that can benefit Yearn, for example by providing liquity to a YFI pair on SushiSwap. These YFI are not allowed to vote in Governance today, but they should be.
- Remove capital efficiency and governance trade-offs. Similarly, there shouldn't need to be a trade-off between participating in Governance or utilizing YFI efficiently.

### Retire the yGov vault

- Vault no longer needed. Without staking rewards, there is no need for a yGov staking vault that's tied to Governance.
- Staking returns are aenemic. At the time of this writing, the APY estimate is 0.9% annually [6]. This is not competitive, and may even dissuade YFI holders from participating in governance. In comparison, Binance recently announced up to 4.49% APY for staking YFI.[7].

### Future possibilities

- Introduce contributor retention program, with vesting YFI rewards to create long term skin-in-the-game for existing and new contributors.
- Re-introduce dividends once Yearn has matured and protocol income no longer can be re-invested as efficiently into growth.
- Introduce a conventional vault for YFI, using the v2 vault design. Such a vault would not be related to governance or staking rewards, and would be free to pursue other, to-be-determined strategies.

## Specification

### Replace staking rewards with buybacks

#### Buy back YFI

- All funds that are used for YFI staking rewards are to be used to buy back YFI. Staking rewards cease until further governance action.
Buybacks should be handled in a continuous and automated way, and not be discretionary or requiring any sign-offs.
- Care should be taken to avoid creating arbitrage or front-running opportunities. Detailed specification of design is left to the developers implementing.

#### Use of bought YFI

- There are no changes in how funds are spent.
- The YFI bought back flows into the Operations Fund established by YIP-54 and can be spent accordingly.
- Example of current spends include: Security audits, Bug bounties, Contributor funding, Grants, Gas reimbursment, Development overhead. See the recently published quarterly financial report[8] for a detailed breakdown.

#### Widen YFI accepted for Governance voting

- Link snapshot to use guest-list[9] to determine which YFI is eligible for voting.
This functionality is already supported and excludes protocols such as Aave which could be utilized in governance attacks. The list of supported protocols is configurable and is being reviewed continuously, improvements and suggestions can be submitted to the repo.
- Any YFI in the Yearn Treasury / Operations Fund is not eligible to vote.
- Retire YFI Governance vault
- Retire the ygov.finance[10] staking vault and the YFI yVault YFIGovernance strategy that relies on it.

## Changelog

- Jan 13: Clarified voting specification to explicitly state that YFI in the treasury cannot be used to vote. [DL]

_Source: [Snapshot](https://snapshot.org/#/yearn/proposal/Qmb6gBzjvgLMazSrQQGVcjutLNdkVyM2Lh6yckMzdoaHWZ)_

## References

1. https://gov.yearn.finance/t/yip-54-formalize-operations-funding/
1. https://gov.yearn.finance/t/proposal-rethinking-capital-allocation/
1. https://gov.yearn.finance/t/proposal-yfi-governance-vault-yacademy/
1. https://www.placeholder.vc/blog/2020/9/17/stop-burning-tokens-buyback-and-make-instead
1. Data available upon request.
1. https://stats.finance/yearn
1. https://www.binance.com/en/support/announcement/de1dfcb0846a422a9d1f50f98ee0e8b8
1. https://github.com/iearn-finance/yearn-pm/blob/master/financials/reports/2020Q3-yearn-quarterly-report.pdf
1. https://github.com/banteg/guest-list
1. https://ygov.finance/

## Information

| Name                | Value                                      |
| ------------------- | ------------------------------------------ |
| Strategie(s)        | erc20-balance-of, yearn-vault              |
| Author              | 0x7A1057E6e9093DA9C1D4C1D049609B6889fC4c67 |
| IPFS                | https://ipfs.fleek.co/ipfs/Qmb6gBzjvgLMazSrQQGVcjutLNdkVyM2Lh6yckMzdoaHWZ|
| Voting System       | Single choice voting                       |
| Start date          | Jan 16, 2021, 10:00 AM                     |
| End date            | Jan 19, 2021, 10:00 AM                     |

## Results

| Result              | Value                                      |
|---------------------|--------------------------------------------|
| Yes                 | 790.83 YFI (99.44%)                        |
| No                  | 4.47 YFI (0.56%)                           |

_Source: [Snapshot](https://snapshot.org/#/yearn/proposal/Qmb6gBzjvgLMazSrQQGVcjutLNdkVyM2Lh6yckMzdoaHWZ)_

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).