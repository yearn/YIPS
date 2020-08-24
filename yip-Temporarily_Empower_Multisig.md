---
yip: <to be assigned>
title: Temporarily Empower Multisig
status: WIP
author: @tTracheopteryx, @Substreight, @franklin501, Michael Anderson, Vance Spencer
discussions-to: https://gov.yearn.finance/t/empower-the-multisig/2891

created: 2020-08-24
---

<!--You can leave these HTML comments in your merged YIP and delete the visible duplicate text guides, they will not appear and may be helpful to refer to if you edit it again. This is the suggested template for new YIPs. Note that an YIP number will be assigned by an editor. When opening a pull request to submit your YIP, please use an abbreviated title in the filename, `yip-draft_title_abbrev.md`. The title should be 44 characters or less.-->
## Simple Summary
<!--"If you can't explain it simply, you don't understand it well enough." Simply describe the outcome the proposed changes intends to achieve. This should be non-technical and accessible to a casual community member.-->
Temporarily empower the Multisig members to make basic, limited operational decisions including budgetary expenditures, protocol grants, and hiring for six months, as we prepare a more robust governance architecture.

## Abstract
<!--A short (~200 word) description of the proposed change, the abstract should clearly describe the proposed change. This is what *will* be done if the YIP is implemented, not *why* it should be done or *how* it will be done. If the YIP proposes deploying a new contract, write, "we propose to deploy a new contract that will do x".-->
The proposed change would allow Multisig members to make personnel & budgetary decisions for no more than six (6) months. Any budget is to be proposed to governance for approval. This change would allow operational decisions to be made at a rapid pace for the next six (6) months. During this six-month term, the Multisig will be responsible for facilitating the creation and transition to a multi-DAO structure. These powers, as well as members of the Multisig, can be removed or modified by governance at any time.

## Motivation
<!--This is the problem statement. This is the *why* of the YIP. It should clearly explain *why* the current state of the protocol is inadequate.  It is critical that you explain *why* the change is needed, if the YIP proposes changing how something is calculated, you must address *why* the current calculation is innaccurate or wrong. This is not the place to describe how the YIP will address the issue!-->
In this nascent stage of Yearn's lifetime, it is crucial to make rapid decisions in order to establish a strong foundation. Structure and support needs to be quickly built around Andre’s development speed in order to ensure the success of the protocol. This proposal formalizes administrative roles that will serve as a foundation for the protocol’s transition to a multi-DAO structure in the near term. 

## Specification
<!--The specification should describe the syntax and semantics of any new feature, there are five sections
1. Overview
2. Rationale
3. Technical Specification
4. Test Cases
5. Configurable Values
-->

### Overview
<!--This is a high level overview of *how* the YIP will solve the problem. The overview should clearly describe how the new feature will be implemented.-->
This proposal grants the Multisig operational authority on the following decisions for six (6) months from implementation: 
    <br>  - Determining and distributing protocol grants.
    <br>  - Determining and distributing community grants.
    <br>  - Determining and distributing legal + DAO consultation grants. 
    <br>  - Identifying and executing key hires listed on the attached budget.
    <br>  - Identifying and engaging security firms. 
    <br>  - Identifying and engaging analytical firms. 
    <br>  - Continue executing yVault strategy changes until a dedicated team can take over.
    <br>  - Facilitating UI & front-end development.
    <br>  - Facilitating business development and integrations. 

This proposal does not grant the Multisig: 
    <br>  - Authority over YFI token or emissions.
    <br>  - Leadership powers beyond those described above.
    <br>  - Any powers over the YIP process or governance.
    <br>  - Authority over the composition of the Multisig group -- any changes to Multisig signers will need to be approved by governance.
    <br>  - The power to ignore or hinder any approved YIPs or the governance process in general.
    <br>  - The power to create a legal entity.

### Rationale
<!--This is where you explain the reasoning behind how you propose to solve the problem. Why did you propose to implement the change in this way, what were the considerations and trade-offs. The rationale fleshes out what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work. The rationale may also provide evidence of consensus within the community, and should discuss important objections or concerns raised during discussion.-->
Forum Poll (202 votes)
<br>78% “Yes, empower the Multisig”
<br>22% “No, find a better solution”

Important objections raised in the forum poll argued against moving to a foundation model and overly centralizing powers. Here is how we’re learning and adjusting from this feedback:
    <br>  - Clarification that this proposal is not for a foundation model and that the yearn governance DAO will retain its dominant authority including the ability to modify or     remove the multisig’s members or powers via future on-chain votes
    <br>  - A deeper discussion about decentralization, governance, and the urgency for this YIP to pass can be found in this thread: Understanding Decentralization & Prioritizing an Operations Team
    <br>  - Clearer limitations on the multisig’s authority detailed above to be controlled via smart contract

### Technical Specification
<!--The technical specification should outline the public API of the changes proposed. That is, changes to any of the interfaces yEarn Finance currently exposes or the creations of new ones.-->

a) Creation of Treasury distribution contract. 
<br>  b) Treasury distribution contract set to redirect any remaining funds and contract will expire after a six (6) month period. 
<br>  c) Cap distribution contract at $200,000 deposit per month. A YIP must be passed to increase this limit.

### Test Cases
**For:** Empower the Multisig for six (6) months.
<br>**Against:** No changes.

### Proposed Budget
<a href="https://imgur.com/a3W7XPU">Budget</a>

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
