
# CVIN-ID Smart Contracts

## Overview
This repository contains the implementation of smart contracts for the CVIN-ID project. The project aims to develop a secure and decentralized identity system for Connected and Autonomous Vehicles (CAVs) using blockchain technology and Self-Sovereign Identity (SSI) principles. 

### Thesis Abstract
Digital identities and identity systems are being applied to many fields, including for machines in general as well as Connected and Autonomous Vehicles (CAVs). These systems are proving to be valuable for enabling secure communication, and verification of identities or associated information. Furthermore, digital identities enable decentralized and autonomous interactions between vehicles, enhancing security and efficiency in CAV networks. The leading paradigm and standards for building secure identities and supporting infrastructure is tending towards blockchain-based and Self-Sovereign Identity (SSI). In this paradigm, decentralized infrastructure and networks such as blockchains and distributed ledgers are used to build identity systems with primary building blocks of Decentralized Identities (DIDs), the associated data with identities known as Verifiable Credentials (VCs), and security algorithms and protocols such as encryption, signing of messages, and selective disclosure of information. Despite this, no work has been done on the convergence of SSI, CAVs, current decentralized networks, and blockchains, let alone benchmarking and stress testing of the various paradigms of implementing such systems via smart contracts or at least anchoring them to blockchains in some manner.

## Repository Structure

- **contracts/**: Contains the smart contract code.
- **migrations/**: Contains migration scripts for deploying the smart contracts.
- **test/**: Contains test cases for the smart contracts.

## Smart Contracts

The smart contracts in this repository are designed to implement decentralized identity management for CAVs. The main components include:

1. **Decentralized Identifiers (DIDs)**: Unique identifiers that are stored on the blockchain.
2. **Verifiable Credentials (VCs)**: Digital statements that are cryptographically signed and can be verified on the blockchain.
3. **Authentication and Authorization**: Protocols for ensuring secure communication and interaction between CAVs.

## Implementation Details

### Blockchain Integration
The smart contracts are deployed on a blockchain network, leveraging its decentralized nature to ensure security and immutability. This approach aligns with the concepts discussed by [Aggarwal et al.](https://dx.doi.org/10.1109/CCiCT56684.2022.00067) and [Gilani et al.](https://dx.doi.org/10.1109/BRAINS49436.2020.9223312), who highlight the advantages of using blockchain for secure and decentralized identity management.

### Self-Sovereign Identity (SSI)
The implementation follows the SSI principles, giving users full control over their digital identities and personal data. This methodology is supported by the works of [Dixit et al.](https://dx.doi.org/10.1109/LCN53696.2022.9843700) and [Stockburger et al.](https://dx.doi.org/10.1016/J.BCRA.2021.100014), who emphasize the importance of user-centric identity management.

### Security Protocols
Security is ensured through the use of advanced cryptographic techniques, including encryption, digital signatures, and selective disclosure of information. This ensures that only authorized entities can access sensitive data, as discussed by [Bhattacharya et al.](https://dx.doi.org/10.1109/ISNCC49221.2020.9297357).

## Getting Started

### Prerequisites
- Node.js
- Truffle
- Ganache

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/CVIN-ID/CVIN-ID-SCs.git
   ```
2. Install dependencies:
   ```bash
   cd CVIN-ID-SCs
   npm install
   ```

### Deployment
1. Start Ganache:
   ```bash
   ganache-cli
   ```
2. Compile and deploy the contracts:
   ```bash
   truffle compile
   truffle migrate
   ```

### Testing
Run the test cases to ensure the smart contracts work as expected:
```bash
truffle test
```

## Contributing
Contributions are welcome! Please follow the standard fork-and-pull request workflow:
1. Fork the repository
2. Create a new branch (`git checkout -b feature-branch`)
3. Commit your changes (`git commit -am 'Add new feature'`)
4. Push to the branch (`git push origin feature-branch`)
5. Create a new Pull Request

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
