## Rari Capital Fuse Liquidator Bot

### Description

Fuse is a open interest rate protocol (this is fancy jargon for "some contracts that let you deploy a clone of Compound and do whatever u want with it") with lots of juicy liquidation profit to go around (liquidation incentives are typically around 15%!)

If you already have a Compound liquidator bot, this should be an easy task for you, you simply need to keep track of all the new Fuse pools that get created to grab their Comptrollers. We also have some custom methods and contracts to make liquidations easier, but docs are WIP (and they're not crazy gas efficient) so I'd recommend recycling your existing Compound bots instead (but if you are curious: https://github.com/rari-Capital/fuse-liquidator-bot)

You can use the `getAllPools` method on the [`FusePoolDirectory`](https://etherscan.io/address/0x835482fe0532f169024d5e9410199369aad5c77e#readProxyContract) to get an array of pool data which is structured like below:

<img width="300" alt="Screen Shot 2021-07-18 at 10 34 10 AM" src="https://user-images.githubusercontent.com/26209401/126076828-6d2a1c5a-3f57-4957-9090-06ca82c01525.png">

None of this data is likely to be useful to you except for the `comptroller` address, which you can use to plug in to your existing Compound liquidator bot and get liquidating! The Fuse comptroller is forked directly from the typical Compound Comptroller impl you are already familiar with (and if you are not check the Compound documentation at https://compound.finance/docs).

One thing important to note is these pools are filled with some unconventional assets (sOHM, xSUSHI, wstETH, yCurve-LINK, etc) that may require wrapping or unwrapping to sell or liquidate with.

You can view the pools and the assets they contain here: https://app.rari.capital/fuse

### Difficulty

- Low for searchers who already have a Compound liquidator bot
- Medium for searchers who do not already have a Compound liquidator

### Is this a one-off opportunity or is it reocurring?

This is reocurring MEV.
It's typical liquidation MEV on steriods because there's isolated 20 lending pools filled with low-cap and wacky coins.

### Steps to capture MEV

1. Get a list of Comptrollers
2. Connect existing Compound liquidator bot to Fuse Comptroller(s)
3. Build wrappers and unwrappers for unconventional assets like sOHM to sell and liquidate with
4. Profit?

### Other

If you need help don't hesitate to reach out in the Rari Capital Discord: https://discord.gg/HzUMPuT

or DM me on Discord personally: `t11s#1559`
