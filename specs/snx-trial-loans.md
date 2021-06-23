## Liquidating ETH loans from Synthetix's trial loan program
### Description
Synthetix ran a year long trial program of using ETH as collateral for issuing synthetic assets, such as sUSD and sETH. Recently Synthetix governance voted to sunset this program, and as a result any loans using ETH that are still standing will need to be liquidated.

Within the trial loan program there is a function that, when triggered, allows anyone to repay the loan's debt and liquidate their collateral. In return the person that does so gets a % of the collateral they help to liquidate. This provides a substantial incentive to searchers to help Synethix liquidate these loans.

These are the contracts where the trial ETH backed loans are created and can be liquidated [sUSD](https://etherscan.io/address/0xfED77055B40d63DCf17ab250FFD6948FBFF57B82) and [sETH](https://etherscan.io/address/0x7133afF303539b0A4F60Ab9bd9656598BF49E272).

[Here is the governance vote](https://staking.synthetix.io/gov/snxgov.eth/QmbNtV62CSKsw2ojHBxs9QiSK9dP2Nwz6b2fmEMHtLJgoe)

### Difficulty
Moderate.

### Is this a one-off opportunity or is it reocurring?
This is a one-off opportunity which should be available in the coming weeks.

### Steps to capture MEV
1. Flashloan ETH (e.g. from Aave)
2. Swap ETH for sUSD or mint sETH using the wrapper
3. Use sETH or sUSD to repay outstanding loans and liquidate their collateral
4. Receive ETH in return
5. Repay the flashloan
6. The remainer is your profit
