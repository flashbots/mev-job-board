## Liquidate unhealthy debt positions in Aave protocol v2

### Description
The health of the Aave Protocol is dependant on the 'health' of the loans within the system, also known as the 'health factor'. When the 'health factor' of an account's total loans is below 1, anyone can make a liquidationCall() to the LendingPool contract, paying back part of the debt owed and receiving discounted collateral in return.

Any of the deposited assets that are being used as a collateral can be liquidated, when `HF < 1`. A liquidation bot monitoring the user health factor can extract profit by liquidating positions as they go underwater.

### Difficulty
Moderate

### Is this a one-off opportunity or is it reoccurring?
This is a re occurring MEV. As market fluctuates many debt positions go underwater and profitable to liquidate.
Also, With new markets deployed on Aave protocol, opportunity for new Liquidation bot arises.

### Steps to capture MEV

  1. Flashloan debt asset from Aave
  2. Liquidate the bad debt position in exchange for debt asset
  3. Swap part of (or all if you want profit in debt asset) collateral asset to repay flashLoan.
  4. The remaining asset is your profit

### Other
  For liquidation calls to be profitable, you must take into account the gas cost involved in liquidating the loan. If a high gas price is used, then the liquidation may be unprofitable for you.

  Refer [Aave docs](https://docs.aave.com/developers/guides/liquidations) for liquidation details.
