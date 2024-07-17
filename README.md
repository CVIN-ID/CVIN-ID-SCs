# CVIN-ID-SCs
Repository for CVIN smart contract implementations, scenarios, and testing suites.

# CVIN-ID Smart Contracts Repository

Welcome to the CVIN-ID Smart Contracts repository. This repository contains implementations of various ERC standards tailored for decentralized identity (DID) management and smart contract-based accounts. The repository includes:

1. **ERC721** - Non-fungible tokens for digital asset ownership.
2. **ERC725** - Base contracts for managing identities and smart contract-based accounts.
3. **ERC725X and ERC725Y** - Extensions of the ERC725 standard for enhanced functionality.

## Repository Structure

CVIN-ID-SCs/
├── ERC721/
│ ├── contracts/
│ ├── scripts/
│ └── test/
├── ERC725/
│ ├── contracts/
│ ├── scripts/
│ └── test/
├── ERC725XY/
│ ├── contracts/
│ ├── scripts/
│ └── test/
└── README.md


## Getting Started

### Prerequisites
- [Node.js](https://nodejs.org/) (v14 or higher)
- [Hardhat](https://hardhat.org/)

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/CVIN-ID/CVIN-ID-SCs.git
   cd CVIN-ID-SCs
Install dependencies:
   ```bash
   Copy code
   npm install

Compilation
Compile the smart contracts:

bash
Copy code
npx hardhat compile
Deployment
ERC721
Deploying the Regular ERC721 Contract
Deploy the regular ERC721 contract to a local network:

bash
Copy code
npx hardhat run scripts/deployRegular.js --network localhost
Deploying the Monolithic ERC721 Contract
Deploy the monolithic ERC721 contract to a local network:

bash
Copy code
npx hardhat run scripts/deployMonolithic.js --network localhost
Deploying Both ERC721 Contracts
Deploy both the regular and monolithic ERC721 contracts to a local network:

bash
Copy code
npx hardhat run scripts/deployBoth.js --network localhost
ERC725
Deploying the ERC725 Basic Contract
Deploy the ERC725 basic contract to a local network:

bash
Copy code
npx hardhat run scripts/deployERC725Basic.js --network localhost
Deploying the ERC725 Monolithic Contract
Deploy the ERC725 monolithic contract to a local network:

bash
Copy code
npx hardhat run scripts/deployERC725Monolithic.js --network localhost
ERC725X and ERC725Y
Deploying the ERC725X Contract
Deploy the ERC725X contract to a local network:

bash
Copy code
npx hardhat run scripts/deployERC725X.js --network localhost
Deploying the ERC725Y Contract
Deploy the ERC725Y contract to a local network:

bash
Copy code
npx hardhat run scripts/deployERC725Y.js --network localhost
Testing
ERC721
Combined Test Suite
Run the combined test suite for both regular and monolithic ERC721 contracts:

bash
Copy code
npx hardhat test test/combined.js
Extended Test Suite for Regular ERC721
Run the extended test suite for the regular ERC721 contract:

bash
Copy code
npx hardhat test test/regularExtended.js
ERC725
Basic Test Suite
Run the test suite for the ERC725 basic contract:

bash
Copy code
npx hardhat test test/erc725Basic.js
Extended Test Suite for ERC725
Run the extended test suite for the ERC725 contract:

bash
Copy code
npx hardhat test test/erc725Extended.js
ERC725X and ERC725Y
ERC725X Test Suite
Run the test suite for the ERC725X contract:

bash
Copy code
npx hardhat test test/erc725X.js
ERC725Y Test Suite
Run the test suite for the ERC725Y contract:

bash
Copy code
npx hardhat test test/erc725Y.js
Summary
ERC721 Contracts
Regular ERC721 Contract: Deploy using deployRegular.js.
Monolithic ERC721 Contract: Deploy using deployMonolithic.js.
Both Contracts: Deploy both using deployBoth.js.
ERC725 Contracts
Basic ERC725 Contract: Deploy using deployERC725Basic.js.
Monolithic ERC725 Contract: Deploy using deployERC725Monolithic.js.
ERC725X and ERC725Y Contracts
ERC725X Contract: Deploy using deployERC725X.js.
ERC725Y Contract: Deploy using deployERC725Y.js.
Conclusion
This repository provides a comprehensive framework for managing digital identities and smart contract-based accounts using ERC721, ERC725, ERC725X, and ERC725Y standards. Each implementation includes detailed test suites to ensure robust and secure functionality. The monolithic versions are included for comparative analysis and benchmarking purposes, while the regular versions are recommended for standard deployment and development.

For more detailed information on each implementation, refer to the respective directories and README files.

For further details and contributions, visit the CVIN-ID GitHub Repository.

go
