## VUSD stable coin arbitrage with (USDC/DAI)

### Description

VUSD is stable coin from Vesper. It provides arbitrage opportunity with other stable coins (USDC/DAI)

__Contract Details__

VUSD liquidity is available on [Uniswap V3](https://info.uniswap.org/#/pools/0xf62b5084ca88cc3cbca6b4ebe68db5fc6f27ee76)

[VUSD Minter Contract](https://etherscan.io/address/0xb652Fc42E12828F3F1b3e96283b199E62EC570Db#code)  (Convert DAI/USDC to VUSD). No fee is applicable on mint.

[VUSD Redeemer contract](https://etherscan.io/address/0x7915CE4F43E1378f0C3720351A973A023F7fB3e8#code) (Convert VUSD to USDC/DAI). The 0.3% fee is applicable on redeem amount.

[Uniswap V3 Router](https://etherscan.io/address/0xE592427A0AEce92De3Edee1F18E0157C05861564) - Dex to swap tokens

[VUSD](https://etherscan.io/address/0x677ddbd918637E5F2c79e164D402454dE7dA8619) - Vesper stable coin

[USDC](https://etherscan.io/address/0xA0b86991c6218b36c1d19D4a2e9Eb0cE3606eB48) - Stable coin

[DAI](https://etherscan.io/token/0x6b175474e89094c44da98b954eedeac495271d0f) - Maker DAI Stable coin

### Difficulty

Moderate

### Is this a one-off opportunity or is it reoccurring?

Ongoing reoccurring opportunity

### Steps to capture MEV

*Option 1*
1. Swap ETH to USDC/DAI on Uniswap V3.
2. Convert USDC/DAI to VUSD using Minter contract
3. Swap VUSD to ETH on Uniswap V3.

*Option 2*
1. Swap ETH to VUSD on Uniswap V3.
2. Convert VUSD to USDC/DAI using Redeemer contract
3. Swap USDC/DAI to ETH on Uniswap V3.

### Other
NA