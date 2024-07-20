
# CVIN-ID Smart Contracts

## Overview
This repository contains the implementation of smart contracts for the CVIN-ID project. The project aims to develop a secure and decentralized identity system for Connected and Autonomous Vehicles (CAVs) using blockchain technology and Self-Sovereign Identity (SSI) principles. This work builds upon the earlier CVIN paper, expanding it by implementing and analyzing six different paradigms of SSI for CAVs.

### Thesis Abstract
Digital identities and identity systems are being applied to many fields, including for machines in general as well as Connected and Autonomous Vehicles (CAVs). These systems are proving to be valuable for enabling secure communication and verification of identities or associated information. Furthermore, digital identities enable decentralized and autonomous interactions between vehicles, enhancing security and efficiency in CAV networks. The leading paradigm and standards for building secure identities and supporting infrastructure are trending towards blockchain-based and Self-Sovereign Identity (SSI). In this paradigm, decentralized infrastructure and networks such as blockchains and distributed ledgers are used to build identity systems with primary building blocks of Decentralized Identities (DIDs), the associated data with identities known as Verifiable Credentials (VCs), and security algorithms and protocols such as encryption, signing of messages, and selective disclosure of information. Despite this, little to no formal or published work has been done on the convergence of SSI, CAVs, current decentralized networks, and blockchains, let alone benchmarking and stress testing of the various paradigms of implementing such systems via smart contracts or at least anchoring them to blockchains in some manner.

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
The implementation follows the SSI principles, giving users full control over their digital identities and personal data. This methodology is supported by the works of [Dixit et al.](https://dx.doi.org/10.1109/LCN53696.2022.9843700) and [Stockburger et al.](https://dx.doi.org/10.1016/J.BCRA.2021.100014), who emphasize the importance of user-centric identity management. Adhering to W3C SSI Standards, this implementation ensures interoperability and compliance with global identity management frameworks.

### Security Protocols
Security is ensured through the use of advanced cryptographic techniques, including encryption, digital signatures, and selective disclosure of information. This ensures that only authorized entities can access sensitive data, as discussed by [Bhattacharya et al.](https://dx.doi.org/10.1109/ISNCC49221.2020.9297357).

## Paradigms Implemented

This repository implements six different paradigms for SSI in CAVs, each based on different ERC standards:

1. **ERC721**: Standard for non-fungible tokens.
2. **ERC725 Base**: Standard for proxy accounts.
3. **ERC725x and y**: Extensions of ERC725 for more complex identity management.
4. **ERC1056**: Lightweight identity standard.
5. **LSP8**: Lightweight verifiable claims.
6. **ERC1055**: Standard for digital assets.

### CVIN SSI System Architecture
The CVIN SSI system architecture is implemented in six different ways, primarily based on the three pillars of building blocks of SSI done as Smart Contract standards (ERCs). These are DIDs, VCs, and Repositories (ERC740). Each of these is implemented in six different ways, resulting in 18 different parts or smart contracts. These implementations are analyzed, configured for CAVs and the Internet of Vehicles (IoV), and benchmarked to be the first to analyze and implement the intersection of SSI, CAVs, IoV, and public blockchains that run on smart contracts.

### W3C SSI Standards and MOBI VID Standards
The implementation adheres to the W3C SSI standards and incorporates the MOBI VID I and II standards for vehicle identity management. These standards ensure interoperability and compliance with global identity management frameworks. The MOBI VID standards are crucial in providing guidelines for the identification and authentication of vehicles, ensuring secure and reliable interactions within the IoV ecosystem.

## Fields of Study

### Self-Sovereign Identity (SSI)
SSI is a decentralized and user-centric approach to digital identity, where individuals and entities have full control over their identity information. This contrasts with traditional centralized identity systems, providing enhanced privacy, security, and interoperability. SSI utilizes technologies such as Decentralized Identifiers (DIDs) and Verifiable Credentials (VCs) to enable secure and verifiable identity transactions.

### Connected and Autonomous Vehicles (CAVs)
CAVs represent the future of transportation, integrating advanced communication, sensing, and control technologies to enable vehicles to operate autonomously and interact with each other and the surrounding infrastructure. Secure and reliable identity management is critical for ensuring the safety and efficiency of CAV networks.

### Internet of Vehicles (IoV)
The IoV extends the concept of the Internet of Things (IoT) to vehicles, creating a network where vehicles, infrastructure, and other entities communicate and interact seamlessly. The IoV aims to improve traffic management, enhance safety, and provide new services to users. Decentralized identity management plays a pivotal role in ensuring the security and trustworthiness of interactions within the IoV.

## CVIN-SC Intersection
The CVIN-SC project lies at the intersection of SSI, CAVs, and IoV, leveraging public blockchains and smart contracts to create a secure and decentralized identity management system. By implementing six different paradigms based on various ERC standards, this project aims to provide a comprehensive analysis and comparison of different approaches to SSI for CAVs and IoV. The goal is to benchmark these implementations, highlighting their strengths and weaknesses, and provide valuable insights for future developments in this field.

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
