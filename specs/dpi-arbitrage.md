## MEV-$DPI liquidity migration - Impact arbitrage oppertunities

### Description

INDEXcoop.com are stopping liquidity mining the uniswap v2 pool in the next 24 hours.

As a result we expect AUM and liqudity in the v2 pool to drop:
https://v2.info.uniswap.org/pair/0x4d5ef58aac27d99935e5b6b4a6778ff292059991

and liquidity / volume to increase in this pool
https://info.uniswap.org/#/pools/0x9359c87b38dd25192c5f2b07b351ac91c90e6ca7

(and possibly this one https://analytics.sushi.com/pairs/0x34b13f8cd184f55d0bd4dd1fe6c07d46f245c7ed )

https://www.coingecko.com/en/coins/defipulse-index#markets

$DPI arbitrage (by bots) is currenlty focused on the v2 pool with both mint and redeem Arb and arb between pools:

e.g. https://etherscan.io/tx/0x5095875c5c6c98196c7302189d81808f57f9a8de0bd64690ce33879b5a264de5 

The other DEX pools look like they arb back to the v2 pool. e.g.

https://etherscan.io/tx/0x8b76722c65402bf46b9a9c9bd4195aec72ea90fc42bdefe560e8478d7ebf34ae


If the expected change in v2 liquidity AUM happens, then I expect that the v3 pool will become the one with deepest liqudity close to the rpice point and so the best oppertunity for issue / redemption arb.

### Difficulty

Moderate (??) - 

### Is this a one-off opportunity or is it reoccurring?

Ongoing oppertunity as DPI dex price drifts off the NAV.

### Steps to capture MEV

List the steps that need to be taken to capture MEV from your protocol. As an example:

1. Monitor DPI NAV and Dex price.
2. Swap ETH for underlyign tokens using DEX liquidity.
3. issue DPI from based on the set issuance contract ( https://etherscan.io/address/0xd8ef3cace8b4907117a45b0b125c68560532f94d ) 
4. Sell DPI for ETH.
5. The remainder is your profit

### Other

INDEXcoop discord (or Set protocol discord) may be able to help.
