## MEV-Opportunity at Gro protocol

### Description
Gro protocol is launching a series of AMM pools including their three native assets: GRO, Vault (GVT) and PWRD. Both GVT and PWRD are tokenised representations of a stablecoin investment position, and can be redeemed at Gro protocol for the value of the underlying stablecoins.

This presents arbitrage opportunities whenever pricing in an AMM is off-peg vs the underlying asset pricing available from Gro protocol.

The opportunity can be captured by understanding the pathways for swapping the assets, and how to convert back into stablecoins using Gro protocol, and then creating arbitrage bots to automate this process.  

The relevant contract addresses are at https://docs.gro.xyz/gro-docs/developer-apis/contracts

And you can read more about Gro here: https://docs.gro.xyz/gro-docs/ or at https://gro.xyz

### Difficulty
Low: this is a arbitrage opportunity between well established DeFi protocols (Uniswap, Curve) and Gro protoco

### Is this a one-off opportunity or is it reoccurring?
This is a reoccurring opportunity as the relevant pools will be incentivised and remain for the indefinite future. However the biggest MEV opportunity will be at the launch of the pools and the immediate days and weeks following, as this is when the market will present most arbitrage opportunities due to thinner pool liquidity and less established pathways.

### Steps to capture MEV

As the price point of Gro protocol’s native assets (GRO,PWRD,GVT) drift off peg (GVT or PWRD are collateralised by stables) or deviate from the exchange rate in other pools (GRO) there is an opportunity to buy assets at a discount vs minting them from the protocol, or sell them at a premium vs burning them in the protocol. Because Gro protocol will incentivise only pools containing its own assets and no pairs with well-established assets (e.g. ETH or USDC) there is a risk that minting and redeeming PWRD/GVT through the deposit and withdrawal handler contracts of Gro protocol become bottlenecks for efficient pricing of GRO for the rest of the market.

#### Scenario 1)
See that PWRD is trading above $1 in any AMM
Mint PWRD from USDC/DAI/USDT in gro protocol
Swap PWRD into overpriced AMM and receive more USDC/DAI/USDT than was used to mint PWRD

#### Scenario 2)
See that there PWRD is either over or underweight in the Curve Metapool.
Buy/sell PWRD to/from Metapool at discount/premium

#### Scenario 3)
See that GRO in Uniswap with GVT (soft-pegged to $204) is trading at a discount/premium vs GRO in Uniswap with PWRD3CRV (soft-pegged to $1)
Either mint GVT or PWRD through Gro protocol then buy GRO from either uni pool at a discount and and trade it into the other pool for extra GVT or PWRD.


#### Protocols involved
Uniswap v2
Curve Factory Metapool
Gro protocol

#### Tokens involved
Gro protocol native tokens
GRO (0x3ec8798b81485a254928b70cda1cf0a2bb0b74d7): valueless governance token with a free floating market value.
PWRD (0xf0a93d4994b3d98fb5e3a2f90dbc2d69073cb86b): rebasing stablecoin. Yield accrues through a rebasing of the balanceof. Redeemable through Gro protocol at a 0.5% withdrawal fee of the underlying.
GVT (0x3adb04e127b9c0a5d36094125669d4603ac52a0c): depository receipt into the Vault product that accrues yield as underlying redeemable stablecoins. Redeemable through Gro protocol at a 0.5% withdrawal fee of the underlying.
Curve’s factory metapool: 50% PWRD, 50% 3CRV (USDT/DAI/USDC)

### Other
  
Time is of the essence for this project! Pools are being launched on Friday 1 October and arbitrage opportunities are likely to begin immediately.

To contact the team please contact Hannes or Charlie at:

Telegram: https://t.me/Graadient or @charliem216
Twitter: @graadient or @charliem2161
Discord: graadient | gro#0001 or Charlie | Gro#2698
Email: hannes@gro.xyz or charlie@gro.xyz
  
