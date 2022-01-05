Solidity Staking Project
========
A standalone Solidity smart contract that will allow users to deposit (stake) a single ERC-20 compatible token into a DApp on Ethereum blockchain. Users will be awarded for staking in this smart contract with an ERC-20 token at a variable rate per hour. Early withdraws that happen before X number of days from their initial deposit will incur a 10% fee, which is burned, this amount is calculated from the total amount of their reward. Deposit longevity reward bonuses will happen every X number of days that increase the reward the staker will receive.

Contract Description
========
Description of the staking Solidity smart contract and reward token smart contract specifics.

Deposit
-------
Users will be allowed to deposit (stake) a specific ERC-20 token into the staking contract. This deposit will transfer the tokens from the original holders wallet to the staking contract. The user will be stored as a staker while preserving their address, amount staked, and the timestamp of the date this event occurred. In the case the user is already staking and wishes to add more to their balance the smart contract should automatically apply their reward to their total balance and adjust the timestamp.

The smart contract will only allow deposits within the bounds of an adjustable start time and end time.

Withdraw
-------
Users can withdraw their tokens and the rewards they have accumulated at anytime. Reward amount is calculated based on the reward variable rate per hour parameter. There will be a 10% early withdraw fee that is placed on the total amount of their reward if the withdraw occurs before X days from the initial deposit. Additionally there will be multiple tiers of longevity reward bonuses for users that have left their funds in the contract for X number of days, e.g 30 days 1.2x bonus, 60 days 1.5x bonus.

Rewards are calculated on withdraw, however the staking contract will need to account for end time. Users should not receive additional rewards past the end time.

Claim
-------
Inside the withdraw function, or possibly a separate function, the user should be able to simply claim their staking rewards without removing their initial deposit. By claiming rewards this also resets the date they deposited tokens and their longevity reward bonus will be reset.


ERC-20 Mintable Reward Token
-------
A standard ERC-20 token based on [OpenZeppelin 4.x ERC-20](https://docs.openzeppelin.com/contracts/2.x/erc20) with the [ERC20Mintable](https://docs.openzeppelin.com/contracts/2.x/api/token/erc20#ERC20Mintable) extension will need to be created that will allow the staking contract to mint rewards. 

Specifications
-------
On contract deployment here are the expected parameters and/or configurations.

- Accepted deposit token contract address
- Reward token contract address
- (adjustable) Reward variable rate per hour
- (adjustable) Multiple longevity reward bonuses
- (adjustable) Early withdraw fee
- (adjustable) Early withdraw day count, e.g. when the fee is applied
- Staking contract start time
- (adjustable) Staking contract end time

Testing Suite
-------
A basic test suite in [Hardhat](https://hardhat.org/) will need to be created to test the following cases:

- deposit
- deposit (add more to balance)
- deposit before and after start / end date
- withdraw with early withdraw fee
- withdraw with no fee
- withdraw with longevity bonus
- withdraw after end date
- any additional tests that you think will be required

Deployable
-------
Inside the repo should include a README that includes information required for deployment with easy to edit `env` variables. [Hardhat](https://hardhat.org/) is required.

References, helpful guides, and code examples
--------
https://itnext.io/creating-a-inheritable-staking-contract-in-solidity-7804ae2d7a32

https://github.com/trusttoken/TrustToken-smart-contracts/blob/master/staking.sol

https://github.com/Synthetixio/synthetix/blob/develop/contracts/StakingRewards.sol


Subgraph Description
========
A basic subgraph to track staking data will be required via The Graph for the frontend. You can get started with their [Quick Start](https://thegraph.com/docs/en/developer/quick-start/). There is also a code example in the [example subgraph](https://github.com/graphprotocol/example-subgraph) repo you can preview.

More practical examples can be found in [SushiSwap's subgraph repo](https://github.com/sushiswap/sushiswap-subgraph/tree/master/subgraphs) as well.


Website 
========
A website that allows users to interact with the staking contract will need to be created.

Design
-------
You can find the design for the site here, (pending)

Technology
-------
ReactJS is required for the frontend. Typescript is required. Ethers.JS is required. Multi wallet support is required for MetaMask / WalletConnect. Project architecture should be well thought out with elements split into components, sections, utilities, helpers, etc.




