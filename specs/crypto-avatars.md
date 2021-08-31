## Mint the 10,000th CryptoAvatars NFT

### Description

[CryptoAvatars](https://cryptoavatars.xyz/) is a NFT project which provides 318Ξ as rewards in two phases to the winners.

For phase 1, the last person who mints the 10,000th CryptoAvatars wins 159Ξ.

For phase 2, the owner of the lucky token wins 159Ξ.

### Difficulty

Low

### Is this a one-off opportunity or is it reoccurring?

It's a one-ff opportunity.

### Steps to capture MEV

For phase 1:

1. Listen on event: `CreateAvatar(tokenId)`
2. when token id 9998 minted, use Flashbots to call `purchase(1)`, put tx of token id 9998 and your tx in to a bundle
3. check if you are the `phase1Winner`
4. call `claimPhase1Jackpot` to receive 159Ξ

Try phase 2 to win another 159Ξ if you can control the lucky token id.

### Other

[Etherscan CryptoAvatars](https://etherscan.io/address/0xf86c665839a0412a3c1fa184a126f2f529e6f046)

[Twitter](https://twitter.com/crypto_avatars)
