# Smart Contracts



Tokens layered on the NFTs can be yield bearing (such as Aave aTokens). The yield from tokens embedded in NFTs can be directed towards buying ReFi tokens and furthering the number of tokens layered on the NFT (as well as holders of ReFi tokens: the NFTs).

FeNXT Smart Contract Scope

Required smart contracts and integrations

### Tech Stack

* **Language:** Solidity and JavaScript
* **Framework:** Hardhat
* **Base Contracts:** SeaPort, ERC721, Charged Particles, ERC20
* **Others:**
  * Ethers
  * Waffle
  * NodeJS
  * Chai

### Primary Functions

A primary NFT marketplace that utilizes platform fees to fund public goods, high impact charities and build liquidity for it's native token. Core marketplace functionality will be built on Seaport:

The SeaPort protocol manages conduits and zones for exchanging ERC20, ERC721, ERC1155 and native tokens. It has huge potential in terms of optimizations and estensibility. ( https://docs.opensea.io/v2.0/reference/seaport-overview )\


**FeNXT ERC20 Token**

* Basic ERC20-permittable token
* The minted token fills a rewards contract for market mining and protocol owned liquidity (POL)\


**ERC20 Distributor Contract**

* Holds staked FeNXT tokens for distribution by the custom Seaport conduit
* Holds FeNXT tokens for protocol owned liquidity
* Can stake FeNXT tokens and supply liquidity to a standard AMM liquidity pool\


**Platform Fee Collector and Distributor Contract**

* Arbitrary but enforced execution hash mapping
* Multi-send for batching ERC20 sends
* Extensible\


**Phoenix NFTs (ERC721 + Charged Particles)**

* Transfer requirements; IE must be charged with a set amount of FeNXT tokens before they can be transferred
* Minting restriction IE cannot be minted when an address already holds one
* Rise From The Ashes transformation - allowing a significantly charged Phoenix to transform by burning the underlying FeNXT token\


**Custom Conduit**

* Handles marketplace mining by _**charging**_ the user's Phoenix NFT everytime an order is fulfilled
* Works specifically with WETH transfers\


**Gnosis Safe Multisig and Configuration**

* Will own the ERC20, ERC721, Phoenix NFT, Fee Collector and Conduit contracts
* Documentation for executing custom contract interactions from the multi-sig
