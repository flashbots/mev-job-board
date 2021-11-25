## Liquidate unhealthy wstETH vaults in Maker protocol

### Description
When the wstETH vault becomes undercollateralized, it is put up for liquidation. The issue with wstETH token is that it's a wrapper over stETH token, and the majority of liquidity for it is in form of liquidity for stETH, and most of it in form of stETH:ETH pool on Curve.

A liquidation bot should be able to win an auction, and then unwrap wstETH to sell to ETH then to DAI.

### Difficulty
High (if from scratch)
Easy (if from an existing maker liquidation bot)

### Is this a one-off opportunity or is it reoccurring?
This is a re occurring MEV. As market fluctuates many debt positions go underwater and profitable to liquidate.

### Steps to capture MEV

  1. Flashmint the required DAI amount
  2. Liquidate the bad debt position with flashminted DAI 
  3. Swap part (or all if you want profit in debt asset) of collateral asset to repay flashmint: wstETH straight on balancer and wsteth-DAI pair on Sushi; unwrap and liquidate steth->eth on curve and eth->dai on DEXes.
  4. The remaining asset is your profit

### Other
  For liquidation calls to be profitable, you must take into account the gas cost involved in liquidating the loan. If a high gas price is used, then the liquidation may be unprofitable for you.

  For more details see https://github.com/makerdao/auction-demo-keeper
