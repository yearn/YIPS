---
yip: 38
title: Distribute / Keep Balancer Rewards
status: Implemented
author: Klim K (@milkyklim)
discussions-to: https://gov.yearn.finance/t/yip-38-distribute-keep-balancer-rewards/2436

created: 08/18/2020
---

<!--You can leave these HTML comments in your merged SIP and delete the visible duplicate text guides, they will not appear and may be helpful to refer to if you edit it again. This is the suggested template for new SIPs. Note that an SIP number will be assigned by an editor. When opening a pull request to submit your SIP, please use an abbreviated title in the filename, `sip-draft_title_abbrev.md`. The title should be 44 characters or less.-->

## Simple Summary
<!--"If you can't explain it simply, you don't understand it well enough." Simply describe the outcome the proposed changes intends to achieve. This should be non-technical and accessible to a casual community member.-->
Keep seized $BAL tokens as part of operational capital instead of distributing to old governance pool $BPT stakers.

## Abstract
<!--A short (~200 word) description of the proposed change, the abstract should clearly describe the proposed change. This is what *will* be done if the SIP is implemented, not *why* it should be done or *how* it will be done. If the SIP proposes deploying a new contract, write, "we propose to deploy a new contract that will do x".-->
~891 $BAL (~18500$) tokens were sent to one of the previous distribution pools. These tokens are seized and sitting in the multisig wallet now. We either have to distribute them or keep them for operational capital.

## Motivation
<!--This is the problem statement. This is the *why* of the SIP. It should clearly explain *why* the current state of the protocol is inadequate.  It is critical that you explain *why* the change is needed, if the SIP proposes changing how something is calculated, you must address *why* the current calculation is innaccurate or wrong. This is not the place to describe how the SIP will address the issue!-->
Since $BALs belong to BPT stakers it is essential to decide what we should do with tokens.

However, the amount of $BAL seized is 3 times lower than protocol fees generated within a week (18k vs 60k). Therefore, I propose to keep $BALs in the multisig and count them towards operational capital, rather than writing a custom claim contract – this solution saves time and gas.

## Specification
<!--The specification should describe the syntax and semantics of any new feature, there are five sections
1. Overview
2. Rationale
3. Technical Specification
4. Test Cases
5. Configurable Values
-->

### Overview
<!--This is a high level overview of *how* the SIP will solve the problem. The overview should clearly describe how the new feature will be implemented.-->
Largest staker should get ~31% (~5735$) of all $BAL tokens, see graph:

https://explore.duneanalytics.com/embed/query/7901/visualization/15749?api_key=8AAmxEmXrkxj56sw0hjDtrVbMN7jZtmsZ6SmZfFo 4

While this might sound impressive there are a bunch of small stakers eligible for less than 8$. Taking into account current gas prices, fact that people have to claim their $BAL themselves I argue that it is more reasonable to keep $BAL as operational capital for the team.

Moreover, this proposal saves time as we skip writing a custom distribution contract.

### Rationale
<!--This is where you explain the reasoning behind how you propose to solve the problem. Why did you propose to implement the change in this way, what were the considerations and trade-offs. The rationale fleshes out what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.-->
Taking into account current gas prices, the fact that people have to claim their $BAL themselves I argue that it is more reasonable to keep $BAL as operational capital for the team.

**For:** Keep $BAL for operational capital.

**Against:** Allow stakers to claim $BAL.
