## Arbitraging the sLINK Wrappr with Curve

### Description
Synthetix will be putting in place a contract that mints sLINK for deposits of LINK. The contract will be very similar to the [ethWrappr](https://etherscan.io/address/0xC1AAE9d18bBe386B102435a8632C8063d31e747C). 
The job consists of minting sLINK with LINK (at parity 1-to-1) and selling that sLINK on CRV, given that sLINK is selling for a hefty premium on the market there is a lot of profit on the table that can be made.

[Here is the sip](https://sips.synthetix.io/sips/sip-153) which will be presented by the authors to the Synthetix Council, where anyone can attend and ask questions, refer to [announcements](https://discord.gg/ztptkyBS) for presentation/implementation date.

### Difficulty
Moderate.

### Is this a one-off opportunity or is it reoccurring?
It should be recurring over an extended period of time, given the history with ethWrappr, it can be expected that the minting cap will be set low and raised gradually while fees set high and lowered, so that snx minters can capture some of that MEV profit as well.

### Steps to capture MEV
1. Flashloan LINK
2. Mint sLINK with LINK (wrappr)
3. Swap sLINK for LINK (CRV)
4. Use the purchased LINK to repay the flash
5. The remainder is your profit

[Here](https://etherscan.io/tx/0xb561d0e0c6f96ceeea7cec9ab486df719fdd4f4807d45a65ed87687a8e7ee731) is one arb example with the ethWrappr.