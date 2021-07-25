## Fee distributions for Wild Credit

### Description

Wild Credit earns fees on the interest rate spread. The interest paid by borrowers is partly earned by the LPs and partly by the protocol. Namely, by the `feeReceiver` contract.

These fees need to be converted to WILD and sent to the xWILD contract periodically.

The conversion function has a caller incentive. If the incentive to call the function exceeds the gas cost, there is a MEV opportunity.

### Difficulty

Low

### Is this a one-off opportunity or is it reoccurring?

This can likely be performed daily or as the TVL grows, even multiple times per day. 

### Steps to capture MEV

1. Load a list of the top 20 holders of both LP tokens for a given lending pair.
2. Check their `pendingSupplyInterest`
3. If it's high enough, call `accrueAccount` which will distribute their accrued interest to the `feeRecipient`
4. After getting enough accrued interest, call `convert` function on `feeRecipient`

Alternatively, just call `convert` on the `feeRecipient` if it has enough fees already in it without adding more pending fees by accruing individual accounts.


### Other

Current `feeRecipient` contract can be found in the [controller](https://etherscan.io/address/0x45ee906e9cfae0aabdb194d6180a3a119d4376c4#readContract)

Read Wild Credit docs for more details: https://wild-credit.gitbook.io/wild-credit/

Website: https://wild.credit

[Twitter](https://twitter.com/WildCredit)

[Discord](https://discord.gg/emcBDpwf6G)
