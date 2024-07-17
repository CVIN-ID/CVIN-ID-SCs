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

`npx hardhat test test/regularExtended.js`### Overview of ERC725 Implementations

ERC725 is a standard for managing digital identities on the blockchain. There are several variations and extensions to ERC725, each providing different functionalities suitable for various use cases. The primary implementations include:

1.  **ERC725X** - This extension focuses on generic execution and allows a smart contract to execute calls, deploy contracts, and transfer native tokens.
2.  **ERC725Y** - This extension adds key-value storage to the identity contract, enabling the storage of arbitrary data associated with the identity.

These implementations can be combined to create a comprehensive identity management system.

### Detailed Description of ERC725 Variations

#### ERC725X

-   **Interface ID**: `0x7545acac`
-   **Functions**:
    -   `execute(uint256 operationType, address target, uint256 value, bytes memory data)`: Allows the contract to execute calls, create contracts, and transfer tokens. This function supports different operation types, including `CALL`, `CREATE`, `CREATE2`, `STATICCALL`, and `DELEGATECALL`.
    -   `executeBatch(uint256[] memory operationsType, address[] memory targets, uint256[] memory values, bytes[] memory datas)`: Executes a batch of operations, allowing multiple actions in a single transaction.
-   **Events**:
    -   `Executed(uint256 indexed operationType, address indexed target, uint256 value, bytes4 indexed selector)`
    -   `ContractCreated(uint256 indexed operationType, address indexed contractAddress, uint256 value, bytes32 indexed salt)`

#### ERC725Y

-   **Interface ID**: `0x629aa694`
-   **Functions**:
    -   `setData(bytes32 key, bytes memory value)`: Sets the value associated with a specific key.
    -   `getData(bytes32 key)`: Retrieves the value associated with a specific key.
-   **Events**:
    -   `DataChanged(bytes32 indexed key, bytes value)`: Emitted when data associated with a key is changed.

### Use Cases

These standards can be used separately or together to enhance various types of smart contracts, such as:

-   **Digital Identities**: Managing decentralized identities (DIDs) where ERC725X handles execution and ERC725Y manages associated data.
-   **NFTs and Metadata**: Enhancing NFTs by using ERC725Y to store metadata and ERC725X for dynamic interactions and execution.
-   **Smart Contract-Based Accounts**: Creating flexible and powerful account systems where the account itself can execute transactions and store data securely.

### Implementation in CVIN-ID

For the CVIN-ID project, combining ERC725X and ERC725Y provides a robust framework for managing vehicle identities and related data. This combination supports features such as secure execution of identity-related transactions and flexible storage of vehicle information.
