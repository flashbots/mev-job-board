## Liquidate undercollateralized Troves in Liquity protocol

### Description

Liquity is a decentralized borrowing protocol that allows one to draw interest-free loans (called Troves) in the form of LUSD (a dollar-pegged stablecoin) against Ether used as collateral. Loans need to maintain a collateralization ratio of 110% (in other words an LTV of 90.9%) therefore timely liquidations are vital to maintaining system solvency.

The protocol allows anyone to trigger the liquidation of Troves that don't meet the minimum collateralization requirement. As an incentive, the liquidator receives 0.5% of the liquidated Ether collateral as well as $200 LUSD per each liquidated Trove.

### Difficulty

Low (if starting from example bot)

Medium (if starting from scratch)

### Is this a one-off opportunity or is it reoccurring?

This is a reocurring MEV opportunity. As the price of Ether (in USD) fluctuates, Troves may fall under the minimum required collateralization ratio and become subject to liquidation.

See this Dune Analytics query for statistics on the total liquidation compensation paid out by the protocol so far:
https://dune.xyz/queries/375892/715901

### Steps to capture MEV

1. Monitor the collateralization of Liquity Troves.
2. Select some or all of liquidatable Troves and trigger their liquidation.
3. Pay a cut of the Ether compensation to the miner of the block, to ensure inclusion.
4. Optionally, swap the LUSD compensation for another asset, if you want.

### References

For an existing example of a liquidation bot for Liquity, see https://github.com/liquity/liqbot. Please note that the code is provided as an example to help you get started, and hasn't been extensively tested.

You may also refer to the [Liquity docs](https://docs.liquity.org/faq/stability-pool-and-liquidations) and the [Liquity repo](https://github.com/liquity/dev#liquidation-and-the-stability-pool) for more detail on liquidation.
