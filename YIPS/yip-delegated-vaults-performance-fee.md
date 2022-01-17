---
yip: <to be assigned>
title: Moving vault performance fee from vault to strategy and setting it to zero for all but the last strategy in a delegtion path
status: Proposed
author: human
discussions-to: https://gov.yearn.finance/t/proposal-revising-delegated-vault-fees-part-1/12087
created: 2022-01-16
---

## Authors
@human

## Simple Summary

In this proposal I try to justify the required changes to vault performance fee, so that it will be both
* more justly for investors in a delegation path
* to have more strategies.

## Abstract

I propose to remove the vault performance fee from the vault and instead add a variable to each strategy, so it could be configured what percentage of the strategy yield should be paid to the vault. After this change has been made, this new variable will be set to 10 percent for all strategies but the strategies which are not doing the actual job of yield generation, instead delegating this yield generation job to other vaults.


## Background

Currently, vault performance fee is 20% [1, 2], ten percent for vault and ten percent for the strategist. In delegation process which transfers the investments from one vault to another vault for yield generation, this fee will be charged at least twice for the same investment, once in the originating vault and once in the destination vault (for delegation in more than 2 tiers, the situation will be worse). I think this behavior is not desirable and should be corrected since the fees are being charged for the same yield more than once, although some operations are done for transferring the investment between vaults (like depositing some token and borrowing another one [3]).

Since the strategist part did not get enough votes during initial proposal [4], this YIP is limited to vault share of performance fee. 

##  Motivation

I think the current fee structure for delegated vaults is not appropriate because the investor will pay fees multiple times on the same yield (s)he has collected.

The other problem is that by the current fee structure, some delegate strategies specifically in long delegation chains may become impractical because of high fees.

The logic for supporting not taking the fees more than once, is similar to the practice [5] of preventing double taxation of parent companies on the profits of their subsidiaries.

## Specification

The performance fee for the vault, will be made configurable for each strategy, and the global vault performance fee [6] removed. By doing so, each strategy will have two performance fees, one that goes to the strategist [7] and the other which goes to the vault (The other parts of the code will be updated according to these changes). For strategies in a delegation path but the last one, we will set the vault fee for the strategy to zero, and collect the vault share of performance fee once in the last strategy by setting the new parameter to 10 percent; for other strategies not being in a delegation path this new parameter will be 10 percent to be consistant to what has been implemented before.

## References
1. https://gov.yearn.finance/t/yip-51-set-vault-v2-fee-structure/7752
2. https://yearn.watch/
3. https://medium.com/iearn/delegated-vaults-explained-fa81f1c3fce2
4. https://gov.yearn.finance/t/proposal-revising-delegated-vault-fees-part-2/12149
5. https://ec.europa.eu/taxation_customs/parent-companies-and-their-subsidiaries-european-union_en
6. https://github.com/yearn/yearn-vaults/blob/67e7ddda69c24f6e85a56338a3519a461b20d107/contracts/Vault.vy#L249
7. https://github.com/yearn/yearn-vaults/blob/67e7ddda69c24f6e85a56338a3519a461b20d107/contracts/Vault.vy#L83

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).



