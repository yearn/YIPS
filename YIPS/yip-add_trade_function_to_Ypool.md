---
yip: <to be assigned>
title: Add stablecoin-to-stablecoin autmatic market-making functionality to the Y pool
status: WIP
author: Ali Atiia (@aliatiia)
discussions-to: [https://gov.yearn.finance/t/proposal-bolt-a-cfamm-facility-to-the-y-pool/3434/](Thread 1) [https://gov.yearn.finance/t/proposal-bolt-a-cfamm-facility-to-the-y-pool/3434/](Thread 2)

created: 2020-08-23
requires: None
---

## Simple Summary

Y pool stablecoin depositors (LPs) will have an additional revenue stream in the form of trading fees from a stablecoin-to-stablecoin automatic market-making functionality. This is in addition to the yield they currently earn from having their stablecoins optimally rotated between Compound, Aave and DyDx. To align incentives between LPs and YFI holders: (1) trading fees are split 95% to LPs and 5% to YFI holders (2) upgrades to the trading functionality opt-in.


## Abstract

> In addition to earning yield from optimized lending, stablecoins in the Y pool could also earn trading fees from an automatic market making (AMM) functionality. A trader supplies stablecoin **A** (e.g. Dai) to the Y pool and receives stablecoin **B** (e.g. USDC) in return. The **A**:**B** exchange rate is provided by stablecoin-optimized constant function. Traders pay a fee which goes 95% to Y pool depositors (LPs) and 5% to YFI holders. This aligns YFI-holders' incentives with LPs and compensates them for the valuable services the yEarn ecosystem provides: liquidity network effects, good governance, community-powered improvements and technical prowess, etc.

> _Deposit workflow_: as usual LPs deposit stablecoins to the Y pool by visiting yearn.finance and clicking on a "deposit" tab. But now there is also a checkbox that says "I also would like to contribute my stablecoins for market-making and earn trading fees". LPs that check the box earn lucrative trading fees but are also exposed to the risk of all the stablecoins in the trading pool. Depositors who do not check the box miss out on these fees but they also do not have exposure to stablecoin risks other than the stablecoin they deposited.

> _Trade workflow_: traders go to yearn.finance and click on "trade" tab, input the desired amount of stablecoin to sell and be presented with a quote for the desired stablecoin to be bought. The stablecoin **sold** to the pool is wrapped into yTokens (e.g. USDC -> yUSDC) and begins earning interest yield immediately, and the stablecoin **bought** is unwrapped from yToken into the base (e.g. yDai -> Dai) and given to the trader.


## Motivation

> - Efficiency: remove intermediaries between Y pool LPs and the trading fees they earn should they opt-in to market-make.

> - Security: reduce extra-yEarn-protocol governance risks.

> - Sustainability: the fruits of network effects of the trading facilities is kept within the YFI ecosystem. This captures the value which is otherwise leaked outside the YFI ecosystem. This value comes from trading fees, liquidity network effects, and good governance.

> - Incentive alignment between YFI governors and Y pool's LPs.

> - Usability: better UI/UX for market-making because opting-in to the trading facility is just a check box, not a whole dedicated frontend which adds confusion.

> - Lucrative revenue stream that is rent-free and governance-risk-minimized
> - Compensation for YFI holders for the service they provide to market-making LPs (namely, yEarn optimize the yield for these market-making stablecoins)
> - Increase liquidity network effects of the yEarn ecosystem.
> - Increase YFI's moat against copy-paste clones because


## Specification

### Overview 

> The constant function of the automatic market making function is stablecoin optimized in order to reduce slippage for traders. A similar function to that used in Curve or the upcoming Shell protocol can be used. A buffer of unwrapped stablecoins is kept to reduce gas costs for small depositors. The pool of AMM-participating Y depositors is the same as the current pool except for the additional publicly `call`able `trade()` function as well as backend utility functions that support it. The index token given to depositors is a pro rata claim on of the total stablecoins in the pool. From a UX/UI perspective, LPs can withdraw to their desirable stablecoin. The withdrawal function performs the necessary swaps in the background to provide the withdrawer with the desired stablecoin. For example, if the pool is currently 25% Dai, 25% USDC, 25% USDT, and 25% TUSD and Alice wants to withdraw her share of the pool which is, say, 4%, into Dai only .. then 1% of total yUSDC, yUSDT, and yTUSD is each unwrapped (i.e. withdrawn from lending protocols) and swapped for Dai. That represents 3% of Alice's share. The, then 4% of all Dai is given to Alice.

> The deployment admin key expires soon after deployment. Future upgrades of the AMM facility are opt-in, in a similar fashion to Uniswap -> Uniswap v2 migration. 


### Rationale:

There are three principles: (1) modularity (2) minimalism (3) gas efficiency. The proposed approach above trades some of (3) in exchange for more (1) and (2). The inverse would have been to implement one global pool for both participating and non-participating LPs in market making. This makes the rebalancing more gas efficient Y-pool-wide. But then it's less modulare and more bloated because the pool needs to keep track of the trading fee distribution to participating LPs. This means the current Y pool must be amended.

The stablecoin-optimized function is designed to reduce slippage for traders. But it also assumes that some amount of de-pegging of one stablecoin should be arbitraged away by the market. The curve only becomes "concious" of a catastrophic de-pegging in a stablecoin after a certain threshold, after which the exponential nature of the pegged:depegged quote protects the pool from further draining. This is a risk that LPs should know and understand about all stablecoin-constant functions generally.

The minimal change in UI/UX is to reduce confusion and mental overhead. Opting-in is a simple checkbox. Withdrawal abstracts away the swapping of underlying AMM shares of the withdrawer to the desired withdraw stablecoin(s). The withdraw workflow and UI/UX is exactly the same for both types of LPs: those participating in the AMM and those that are not. Note that both types of LPs earn optimized yield.

### Test Cases

## Copyright

Copyright and related rights waived via [CC0](https://creativecommons.org/publicdomain/zero/1.0/).
