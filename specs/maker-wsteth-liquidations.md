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
  3. Swap part (or all if you want profit in debt asset) of collateral asset to repay flashmint: wstETH straight on balancer and wstETH-DAI pair on Sushi; unwrap and liquidate steth->eth on curve and eth->dai on DEXes.
  4. The remaining asset is your profit

### Other
  For liquidation calls to be profitable, you must take into account the gas cost involved in liquidating the loan. If a high gas price is used, then the liquidation may be unprofitable for you.

  For more details see https://github.com/makerdao/auction-demo-keeper

### References
  - wstETH <-> stETH
    - [wrap](https://docs.lido.fi/contracts/wsteth/#wrap) / [unwrap](https://docs.lido.fi/contracts/wsteth/#unwrap) functions of Lido contract
    - [Official Lido web-interface](https://stake.lido.fi/wrap)
  - Liquidity:
    - stETH-ETH:
      - [Curve](https://curve.fi/steth) (largest, ~ $5,000,000,000)
      - [1inch](https://app.1inch.io/#/1/dao/pools?filter=stETH) (~ $700,000)
    - wstETH-WETH:
      - [Balancer v2](https://app.balancer.fi/?utm_source=medium&utm_medium=blog&utm_campaign=metastablepools#/pool/0x32296969ef14eb0c6d29669c550d4a0449130230000200000000000000000080) (~ $400,000,000)
    - wstETH-DAI
      - [SushSwap](https://app.sushi.com/swap?inputCurrency=0x7f39C581F595B53c5cb19bD0b3f8dA6c935E2Ca0&outputCurrency=0x6B175474E89094C44Da98b954EedeAC495271d0F) (~ $40,000,000)
    - stETH-DAI:
      - [1inch](https://app.1inch.io/#/1/dao/pools?filter=stETH) (~ $10,000,000)
    - stETH-LDO:
      - [1inch](https://app.1inch.io/#/1/dao/pools?filter=stETH) (~ $7,000,000)
    - stETH-USD:
      - [FTX](https://ftx.com/trade/STETH/USD) (Daily volume ~ $80,000)
