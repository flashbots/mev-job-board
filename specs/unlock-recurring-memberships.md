## Renew Memberships on Unlock Protocol

### Description

Unlock Protocol allows anyone to set up a membership program using its **lock** smart contracts. Every lock has keys, and a key is an ephemeral NFT that represents the membership status of its owner.
Keys are priced either in the network's native token, or their currency is an ERC20 token. In the latter case, the holder of the key (a.k.a. member) may approve the lock contract with an allowance, that could cover one or more renewals of the membership, after the key expires.

Since Unlock Protocol released version 10 of its PublicLock contract, there is a new method called `renewMembershipFor`, which allows anyone to renew the expired key of a membership subscriber.

In order to incentivize others to renew the key of a given member, lock owners can set a `gasRefundValue`, which is the amount of the key-prices' ERC20 token, that the senders of the `renewMembershipFor` transactions will receive as reward for their help in keeping the subscriptions recurring.

An example lock on Rinkeby is [0x8E9F8fAb9043a09aF9C35bCB9f9e29e9B0eD1DD3](https://rinkeby.etherscan.io/address/0x8e9f8fab9043a09af9c35bcb9f9e29e9b0ed1dd3 "0x8E9F8fAb9043a09aF9C35bCB9f9e29e9B0eD1DD3").

### Difficulty

moderate

### Is this a one-off opportunity or is it reoccurring?

This opportunity is reoccuring. All memberships can be renewed, whenever a key expires, as long as the owner's ERC20 allowance for the lock contract is sufficient.

### Steps to capture MEV

1. Find relevant locks
2. Find relevant subscribers
3. Find profitable opportunities with locks' `gasRefundValue`s
4. Renew memberships (and optionally swap refunded tokens)

### Other

An example with a basic approach to this on the Rinkeby testnet can be found [here](https://github.com/pwagner/unlock-recurring-mev "here").
