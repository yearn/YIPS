---
yip: 88
title: "Governance Overhaul: DAO Restructuring"
author: 0xPickles and the governance team contributors
discussions-to: https://gov.yearn.fi/t/yip-88-governance-overhaul-dao-restructuring/14553
status: Approved
created: 2025-09-28
---

## Simple Summary
This proposal outlines the operational and financial restructuring of the Yearn DAO to focus all efforts on revenue generation and on-chain accountability.

**IMPORTANT NOTE:** This proposal is the first of three interconnected parts of a single initiative designed to overhaul Yearn's operations, tokenomics, and contributor incentives.

- **Part I: Operations & DAO Restructuring (This Proposal)**
- [Part II: stYFI Tokenomics & Migration](https://gov.yearn.fi/t/yip-88-governance-overhaul-styfi/)
- [Part III: Contributor & Team Incentives](https://gov.yearn.fi/t/yip-88-governance-overhaul-incentives/)

All three parts will be discussed in parallel on the forum but will be voted on as a single, all-or-nothing package in one Snapshot vote for **YIP-88**. If the unified proposal passes, all three parts will be implemented. If it fails, none will be.


## Abstract
**If the complete YIP-88 initiative is adopted**, this part of the proposal will:
- Reorganize Yearn contributors around revenue-earning teams, except for a minimal DAO operations team.
- Require all teams to use on-chain revenue splitters for transparent accounting.
- Mandate on-chain financial reporting to justify all future budget requests.

## Motivation
The primary driver for this proposal is to reorient the entire Yearn DAO towards sustainable **growth and operational excellence**. The idea is to create a transparent and accountable framework that directly supports the value accrual mechanisms detailed in Part II and justifies the incentive structures in Part III.

The motivation for this specific operational model is rooted in several key principles:
*   **Center the org around autonomous, revenue-generating units:** The fundamental principle of this reorg is that teams should be structured as self-sufficient units focused on generating revenue. Each team should encompass all critical functions (e.g., development, strategy, marketing) needed to operate its products. This "full-circle" structure is essential for enabling clear Profit & Loss (P&L) attribution, allowing the DAO to accurately track all earnings and costs associated with each team.
*   **Move accountability on-chain:** Moving from off-chain tracking and manual reporting to on-chain revenue splitters and automated tracking provides unimpeachable, data in real-time. This empowers the DAO to make objective, data-driven decisions about resource allocation, ensuring that we fund what works and that every team's contribution to the bottom line is clear.
*   **Maintain a lean and accountable support system:** Certain core functions are necessary for the DAO to operate. By defining a minimal, well-scoped DAO Operations (DAO-ops) team, we ensure this essential back-office work is supported. Crucially, this team remains fully accountable to the DAO, which can regularly review and justify its scope and budget, preventing operational bloat.
*   **Establish guidelines:** The transition to this new operational model will have complexities. This YIP intentionally avoids micromanaging that process. Instead, it establishes the foundational ground rules and clear end-state goals, empowering the teams themselves to collaborate and forge the most effective paths to implementation.

### 4.1 Alternatives Considered

In developing this proposal, we evaluated several alternative paths for restructuring the DAO. These were considered and rejected for the following reasons:
*   **Merge into a single "Mono-Team":** We considered dissolving all yTeams and consolidating contributors into a single, hierarchical organization. This was rejected as it introduces significant centralization vectors, creates single points of failure in management, and runs counter to the decentralized, autonomous ethos of Yearn. If the management of a mono-team fails, the entire DAO fails with it.
*   **Splinter the DAO completely:** We also considered breaking up the DAO entirely, allowing individual teams or products to spin out as independent entities. This was rejected because it would be massively value-destructive. The Yearn brand carries immense weight, trust, and recognition in the ecosystem, these are assets that have been built over years. Throwing that away would be a disservice to the protocol and all YFI holders.

### 4.2 Out of Scope

- The specific tokenomics of stYFI and revenue distribution mechanics (covered in Part II).
- The allocation of treasury YFI for contributor and team incentives (covered in Part III).

### Background

Yearn's current operational framework is the product of a multi-year evolution aimed at increasing decentralization and contributor autonomy. The foundational shift occurred with the passage of **YIP-61: Governance 2.0**[[1]](#References), which dissolved a centralized operational group in favor of empowering smaller, independent teams (yTeams).

Initially, budget approvals were handled by a dedicated **yBudget** team. Over time, this process evolved further to decentralize decision-making, leading to the current **yBudget II council process**. In this system, all yTeams vote on contributor budget requests (BRs), with revenue-generating teams wielding outsized influence proportional to the revenue they contribute.

This model proved highly effective at instilling fiscal discipline and reducing operational overhead. By giving revenue-generating teams a stronger voice, the DAO successfully aligned its spending with its earnings, leading to significant cost reductions over the past year, essentially cutting the budget in half.

| Metric | yBudget II Epoch 1 (May-Jul 2024) | yBudget II Epoch 5 (May-Jul 2025) | Change |
| :--- | ---: | ---: | ---: |
| **Total Contributor Expenses** | $1,740,000 | $858,000 | **-50.7%** |
| **Average Monthly Expenses** | $580,000 | $286,000 | **-50.7%** |

However, as the DAO has matured, this structure has presented a new set of second-order challenges that now impede our efficiency and focus:

*   **Organizational Misalignment:** The system has seen an increase of non-revenue-earning teams relative to revenue-earning ones. While these teams perform necessary functions, it gives greater influence to initiatives that do not directly impact the bottom line, diluting the focus on profitability.
*   **The Free-Rider & Attribution Problem:** It is difficult to measure and attribute the value created by non-revenue teams. This creates a potential "free-riding" effect by Revenue Teams, where they benefit from the efforts of non-revenue teams, without this being attributed to the right place. This makes it difficult to assess true net profitability of efforts.
*   **Coordination Inefficiency:** The proliferation of many small yTeams, often with overlapping contributors, makes cross-team coordination complex and inefficient. This fragmentation hinders our ability to execute large, cohesive strategic initiatives.

These challenges indicate that while the `yBudget II` process was a successful evolutionary step for instilling fiscal discipline, the next phase of Yearn's growth requires a more streamlined, explicitly revenue-focused operational model. This proposal builds on the successes of the past while directly addressing its emergent limitations.

## Specification
### Overview
This proposal outlines the operational and financial restructuring of the Yearn DAO to focus all efforts on revenue generation and on-chain accountability.

**IMPORTANT NOTE:** This proposal is the first of three interconnected parts of a single initiative designed to overhaul Yearn's operations, tokenomics, and contributor incentives.

- **Part I: Operations & DAO Restructuring (This Proposal)**
- [Part II: stYFI Tokenomics & Migration](https://gov.yearn.fi/t/yip-88-governance-overhaul-styfi/)
- [Part III: Contributor & Team Incentives](https://gov.yearn.fi/t/yip-88-governance-overhaul-incentives/)

All three parts will be discussed in parallel on the forum but will be voted on as a single, all-or-nothing package in one Snapshot vote for **YIP-88**. If the unified proposal passes, all three parts will be implemented. If it fails, none will be.

### Rationale
The rationale is to center the DAO on measurable, revenue-linked accountability while preserving essential DAO-ops functions. This structure addresses coordination inefficiency and attribution problems by tying budgets to on-chain reporting and clearly defined revenue responsibilities.

### Technical Specification
The following numbered requirements will be implemented to execute the operational and financial restructuring of the DAO.

#### 5.1 General Principles

1.  **Revenue-Centric Model**: All Yearn teams, with the exception of the DAO Operations (DAO-ops) team, will be reorganized to focus on specific, measurable revenue-generating activities.
2.  **Team Autonomy**: Revenue-earning teams will operate with a high degree of independence and self-reliance. They are responsible for managing their own product strategy, operations, and budgets to achieve their goals.

#### 5.2 Team Structure & Transition

3.  **Transition Process**: Existing yTeams are required to self-organize, merge, and restructure into cohesive, revenue-generating teams.
4.  **Transition Deadline**: The current yBudget II epoch concludes on **October 31, 2025, 23:59:59 UTC**. After this date, no BRs from non-revenue-earning teams will be approved for funding.
5.  **Hard Cutoff**: Contributors not formally part of an approved revenue-earning team or the DAO-ops team by the transition deadline will no longer be funded on a recurring basis.
6.  **One-Off Project Funding**: Non-recurring (and potentially non-revenue earning) work may still be funded via a direct BR. Such proposals must be for a specific project with a defined scope and end date, and not for ongoing contributor roles.

#### 5.3 DAO Operations (DAO-ops) Team

7.  **Scope Definition**: A single, non-revenue team, DAO-ops, will be maintained with a minimal scope, limited to:
    *   Create and Maintain DAO smart contracts (governance, treasury, rate providers, auctions, YFI tokenomics, etc.).
    *   Build and Maintain DAO governance and reporting infrastructure (budgets, proposals, treasury, voting, etc.).
    *   Performing essential administration directly related to the above tasks, like tweaking parameters, kicking auctions, and optimizing performance of these systems.
8.  **Technical Focus**: The DAO-ops team mandate is strictly technical and administrative. It does not manage community, marketing, social media, or communications, nor does it influence the strategy of revenue-earning teams.
9.  **Budget Approval**: The DAO-ops team must submit a formal Budget Request (BR) for approval following the passage of this YIP to secure funding and commence its work, and will need to continue to submit BRs on an ongoing basis as any other team.

#### 5.4 Revenue & Financial Reporting

10. **On-Chain Revenue Splitters**: All team-generated revenue must be sent to designated splitter contracts on Ethereum mainnet. Teams are responsible for bridging funds to Ethereum mainnet in order to send to splitter contracts.
11. **Initial Routing**: Initially, all splitters will be configured to route 100% of incoming revenue to the Yearn Treasury. This will be updated per the routing rules in Part II.
12. **Approved Revenue Tokens**: Revenue must be sent in a format pre-approved by the DAO-ops team (e.g., stablecoins, WETH).
13. **Mandatory On-Chain Reporting**: All budget requests must be justified by on-chain financial reporting that tracks total revenue contributed versus total budget utilized for that team.
14. **On-Chain Budget Requests**: All team budget requests will ultimately be submitted on-chain using a standardized format to be defined by the DAO-ops team.

#### 5.5 Budgeting Process & Governance

15. **Proposing New Revenue Teams**: Any group may propose a new revenue-earning team, which must commit to the mandatory on-chain reporting framework.
16. **Budget Request (BR) Cadence**: As already is in place, team BRs will continue to be approved for a maximum duration of **three months**.
17. **Fund Streaming**: Approved budgets will by default be streamed using existing contracts. There will be an option to request up-front payment as part of the BR.
18. **Safeguard Mechanism**: yChad, and subsequently the DAO, will retain the ability to halt fund streams in clear cases of underperformance, malicious activity, or misuse of funds.

##### 5.5.1 Discretionary & Fast-Track Funding
19. **Establishment of a Discretionary Fund**: A dedicated, on-chain fund will be established for urgent, sensitive, or unforeseen expenses that cannot go through the standard public proposal process (e.g., critical security audits, stealth projects).
20. **Initial Funding**: The fund will be initialized with **$250,000** worth of stablecoins from the Treasury.
21. **Management and Delegation**: The fund will be managed by yChad, who has the discretion to delegate its management to another designated multi-sig (or the YBC as described in Part III).
22. **Accountability via Top-Up**: The fund can only be replenished via a formal proposal to the DAO. Such proposals must be accompanied by a report justifying past expenditures and are subject to a DAO vote.

##### 5.5.2 Transition to On-Chain Governance
23. **Interim Budget Governance**: Following the transition deadline, budget approvals for the new revenue teams, the DAO-ops team, and any other proposal will continue to be decided by the existing yBudget II council process.
24. **Transition to on-chain governance**: The DAO-ops team is responsible for designing, proposing, and implementing the final on-chain governance system for budget approvals.
25. **Checks and Balances**: The transition to this final system is not automatic. It will occur only when the DAO-ops team deploys the necessary contracts, and yChad provides the final, binding sign-off, acting as a crucial backstop to prevent a premature or flawed rollout. The DAO-ops team's continued funding during the interim period is contingent on making demonstrable progress, as judged by the yBudget II council.
26. **Final Governance Structure**: Once the on-chain system is active, the yBudget II council will be dissolved. All budget decisions will be made via binding votes by stYFI holders. The concept of "team influence" will cease to exist; voting power will derive solely from an individual's or entity's stYFI stake (see part II).

#### 5.6 Governance System Implementation

27. **System Design Mandate**: The DAO-ops team is delegated with the final implementation of the governance system.
28. **Core Design Philosophy**: The guiding principles for development must be **simplicity and security**. Contracts should be as simple and immutable as possible to minimize attack surface.
29. **Modularity**: While individual components should be immutable, the overall system must be modular, allowing for specific components to be replaced or upgraded over time via governance.
30. **stYFI Compatibility**: The voting system must be designed to natively support the specific mechanics of stYFI outlined in Part II (e.g., time-weighted voting).
31. **Leverage, Don't Replicate**: The DAO-ops team should avoid over-complicating the system. It should leverage principles from battle-tested frameworks (e.g., Aragon[[2]](#References), Ajna[[3]](#References), Curve[[4]](#References), yETH[[5]](#References)) where possible but is not expected to be 1:1 compatible, prioritizing a simple and secure implementation that meets the core requirements.
32. **Flexible Cadence**: The specific timing of governance epochs and voting rounds is left to the implementation phase and can be iterated on over time.

### Test Cases
Not specified in the forum post. Implementation details and test cases are deferred to the implementation phase.

### Configurable Values
- Transition deadline: October 31, 2025, 23:59:59 UTC.
- Discretionary fund initial size: $250,000.
- Budget request cadence: up to three months.
- Treasury routing: initially 100% of splitter revenue to the Yearn Treasury.

## References
1. https://gov.yearn.fi/t/yip-61-governance-2-0/10460
2. https://docs.aragon.org/ve-governance/1.0.0/index.html
3. https://faqs.ajna.finance/faqs/grants
4. https://www.curve.finance/dao/ethereum/proposals
5. https://yeth.yearn.fi/vote

## Copyright
Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
