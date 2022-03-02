## OUSD Reward Token Harvesting

### Description

The OUSD Harvester contract collects reward tokens earned by the OUSD strategies, sells them, and sends them on to increase protocol yield. Anyone can call the harvest and earn 1% of the resulting USDT for doing so. Chainlink oracles are used to ensure the sale prices are within limits.

### Difficulty

moderate

### Recurring

This opportunity occurs whenever the USDT to be gained from the harvest is greater than the gas cost to execute the transaction.

### Steps to capture MEV

1. Pick the right moment when it will be profitable
2. Call the harvest

### How to call

To harvest, you call harvester.harvestAndSwap(strategyAddress, rewardTo).

The harvester address and available strategy addresses can be found in the strategy tab of the OUSD [contract registry](https://docs.ousd.com/smart-contracts/registry) docs. There are multiple strategies. Only some strategies may be active at any given time.

The rewardTo address is the account that will receive the USDT funds as a reward for calling the function - use your own address for it.


### Harvest ABI

```
[{
  "inputs": [
    {
      "internalType": "address",
      "name": "_strategyAddr",
      "type": "address"
    },
    {
      "internalType": "address",
      "name": "_rewardTo",
      "type": "address"
    }
  ],
  "name": "harvestAndSwap",
  "outputs": [],
  "stateMutability": "nonpayable",
  "type": "function"
}]
```

### Support

OUSD has a [guide on calling this](https://docs.ousd.com/guides/incentivized-harvesting-guide) in the docs.

If you have a question, feel free to contact a developer in the Orign Dollar discussion channel in the [Origin Protocol Discord](https://discord.gg/w7kEuJs7N2).