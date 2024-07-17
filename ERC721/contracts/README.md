ERC721 Smart Contracts
======================

This directory contains the ERC721 smart contract implementations for "CVIN_NFT_DID_ERC721" and "CVIN_NFT_DID_ERC721_Monolithic".

Overview
--------

The ERC721 standard provides a framework for creating unique, non-fungible tokens (NFTs) on the blockchain. These tokens can represent ownership of any asset, digital or physical. The implementation includes functionalities for identity verification, toll payments, and warranty eligibility checks, emphasizing its utility in scenarios involving identity and secure transactions.

Key Features and Functionalities
--------------------------------

### Ownership Management

-   `owner()`: Returns the address of the current owner of the contract.
-   `transferOwnership(address newOwner)`: Allows the current owner to transfer ownership to a new account.
-   `renounceOwnership()`: Enables the owner to renounce their ownership, making the contract ownerless.

### Token Management

-   `mint(address to, uint256 tokenId, string memory uri)`: Mints a new token with a specific URI to the given address.
-   `balanceOf(address owner)`: Returns the balance of the owner's tokens.
-   `ownerOf(uint256 tokenId)`: Returns the owner of the specified token.
-   `approve(address to, uint256 tokenId)`: Approves another address to transfer the given token.
-   `setApprovalForAll(address operator, bool approved)`: Approves or revokes approval for an operator to manage all tokens.
-   `transferFrom(address from, address to, uint256 tokenId)`: Transfers a token from one address to another.
-   `safeTransferFrom(address from, address to, uint256 tokenId)`: Safely transfers a token, checking that the receiver can handle ERC721 tokens.
-   `tokenURI(uint256 tokenId)`: Returns the URI of the specified token.

### Identity-Based Functionality

-   `recordEntry(uint256 tokenId, uint256 timestamp)`: Records the timestamp of toll entry for a vehicle.
-   `payToll(uint256 tokenId)`: Allows payment of toll using native currency, verified by the token's identity data.

### Royalty Management (EIP-2981)

-   `royaltyInfo(uint256 _tokenId, uint256 _salePrice)`: Returns the royalty information for the given token ID and sale price.
-   `_setTokenRoyalty(uint256 tokenId, address receiver, uint96 feeNumerator)`: Sets royalty information for a specific token.
-   `_setDefaultRoyalty(address receiver, uint96 feeNumerator)`: Sets default royalty information.

Use Case: Decentralized Identity (DID)
--------------------------------------

The ERC721 contract can be utilized for managing digital identities, particularly in the context of connected and autonomous vehicles (CAVs). This involves secure identity verification, toll payments, and eligibility checks for services like extended warranties. The contract provides a robust framework for handling identity-related transactions and maintaining secure ownership records on the blockchain.

Directory Structure
-------------------

-   `contracts/`: Contains the smart contract code.
-   `scripts/`: Contains the deployment scripts.
-   `test/`: Contains the test scripts.

Getting Started
---------------

### Prerequisites

-   Node.js (v14 or higher)
-   Hardhat

### Installation

Install the necessary dependencies:

bash

Copy code

`npm install`

### Compilation

Compile the smart contracts:

bash

Copy code

`npx hardhat compile`

### Deployment

#### Deploying the Regular ERC721 Contract

Deploy the regular ERC721 contract to a local network:

bash

Copy code

`npx hardhat run scripts/deployRegular.js --network localhost`

#### Deploying the Monolithic ERC721 Contract

Deploy the monolithic ERC721 contract to a local network:

bash

Copy code

`npx hardhat run scripts/deployMonolithic.js --network localhost`

#### Deploying Both Contracts

Deploy both the regular and monolithic ERC721 contracts to a local network:

bash

Copy code

`npx hardhat run scripts/deployBoth.js --network localhost`

### Testing

#### Combined Test Suite

Run the combined test suite for both regular and monolithic ERC721 contracts:

bash

Copy code

`npx hardhat test test/combined.js`

#### Extended Test Suite for Regular ERC721

Run the extended test suite for the regular ERC721 contract:

bash

Copy code

`npx hardhat test test/regularExtended.js`


#### Identity-Based Test Suite for Regular ERC721

Run the identity-based test suite for the regular ERC721 contract:

bash

Copy code

`npx hardhat test test/identityBased.js`
