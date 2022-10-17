#Liquidate unhealthy debt positions in Silo Finance V1

##Description

Silo Finance is a lending protocol that implements isolated lending markets with a common bridge asset to achieve security and efficiency.  Each Pool, we cal it a silo, consists of a base token asset (Token A) and ETH, the bridge asset. In order to expedite the process of integrating liquidation bots, the Silo team has put together a repo outlining all the steps to successfully build a liquidation bot: https://github.com/silo-finance/liquidation 

##Difficulty

Moderate.
Silo Contracts are not forks and will require integrations. You can use the liquidation helper repo listed above to fast track the process.

##Is this a one-off opportunity or is it reoccurring?

This is a recurring MEV Liquidation Opportunity. Be sure to watch for new silos as they appear and keep an eye for when more esoteric collaterals get onboarded as these will need some sort of wrapper/unwrapper.

##Steps to capture MEV

###To perform liquidation, you have to have:

- borrower address

- silo address

- Asset address

Collect silo addresses by scanning for IRepository.NewSilo events. Scan every block for IBaseSilo.Borrow events.
Note: watching one address is not enough, because the protocl will have many silos.

With all above you will have all required data.

###Monitoring

All users have to be constantly monitored and checked if they are solvent. Use LiquidationHelper.checkSolvency to do that.

###Removing users from monitoring

Watch for IBaseSilo.Repay events, then for that users, use LiquidationHelper.checkDebt to check, if these users still have any debt left. If not, we can remove them from monitoring list.
They should jump back into a list when we detect them at IBaseSilo.Borrow. Because of above, removing should be done before any other action.

###Liquidation

Once we detect, that user is not solvent, we should immediately execute tx to liquidate him.
Use ISilo.flashLiquidate to do so.

You can also use LiquidationHelper.executeLiquidation to perform liquidation or to see how this process looks in details.Other

##Other

We’re more than willing to help with all things liquidations and work closely with people keeping our network healthy.
If you need help or just wanna talk feel free to reach out on our discord https://discord.com/invite/silo-finance  or contact Tenzent#0038 Directly.
