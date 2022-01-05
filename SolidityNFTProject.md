Solidity NFT Project
======
A Solidity smart contract that will allow only specific users to mint a single [ERC-721](https://eips.ethereum.org/EIPS/eip-721) NFT. The set of addresses that can mint NFTs is determined on deployment. Once an address mints the NFT it can not mint anymore via the smart contract. The NFT that is minted is predefined on launch and will not change. 

Contract Description
========
Description of the NFT minting Solidity smart contract and the NFT itself. This assignment you will be required to utilize [OpenZeppelin ERC-721](https://docs.openzeppelin.com/contracts/4.x/erc721) as a base.

Mint
------
The Solidity smart contract will allow only specific addresses to interact with the mint function. This set of addresses will be defined on deployment and capped at 666 in length. The list of addresses can not be changed or modified after its set. Once an address from this list mints a single NFT they can not mint one again. There will not be any internal fee or cost to mint the NFT, besides the gas fee paid by the user making the transaction.


Start & End
------
This smart contract will have a start block and end block so minting can only be done within the bounds of these two block ranges.


ERC-721 NFT
------
All metadata and image for the NFT must be stored on [IPFS](https://ipfs.io/). The `id` attribute will start at 1 and increment by 1 for each time an address mints a new NFT.

**Metadata sample**

```JSON
{
  "name": "sample name",
  "description": "sample description",
  "image": "ipfs://image.png",
  "webm_url": "ipfs://image.webm",
  "attributes": {
    "id": "0"
  }
}
```

Specifications
-------
On contract deployment here are the expected parameters and/or configurations.

- Configurable predefined NFT metadata
- A list of addresses that are enabled to mint 1 NFT
- A start and end block


Testing Suite
-------
A basic test suite in [Hardhat](https://hardhat.org/) will need to be created to test the following cases:

- mint from address in list
- mint from address not in list
- mint multiple times from same address
- mint multiple times from different addresses
- mint before and after start/end time
- transfer NFT ownership

Deployable
-------
Inside the repo should include a README that includes information required for deployment with easy to edit `env` variables. [Hardhat](https://hardhat.org/) is required.

References, helpful guides, and code examples
--------
https://betterprogramming.pub/how-to-create-nfts-with-solidity-4fa1398eb70a

https://medium.com/coinmonks/guide-to-creating-your-own-nft-with-javascript-solidity-part-1-of-3-7909b80fae94

https://docs.ipfs.io/how-to/mint-nfts-with-ipfs/#a-short-introduction-to-nfts

Website
========
A basic website that will allow users to connect their web3 compatible wallet and mint NFTs via the smart contract

Design
-------
You can find the design for the site here, (pending)

Technology
-------
ReactJS is required for the frontend. Typescript is required. Ethers.JS is required. Multi wallet support is required for MetaMask / WalletConnect. Project architecture should be well thought out with elements split into components, sections, utilities, helpers, etc.

