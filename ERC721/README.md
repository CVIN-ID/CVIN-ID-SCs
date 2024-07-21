
# Implementation Variation I: ERC721

## Overview
This implementation variation focuses on using the ERC721 standard for non-fungible tokens (NFTs) to manage digital identities for Connected and Autonomous Vehicles (CAVs). By leveraging the unique properties of ERC721 tokens, we create a robust and secure identity management system that ensures each vehicle has a unique, verifiable identity on the blockchain.

### ERC721 Standard
ERC721 is a widely adopted standard for creating non-fungible tokens on the Ethereum blockchain. Non-fungible tokens are unique and cannot be exchanged on a one-to-one basis with other tokens, making them ideal for representing distinct entities such as digital identities. Key functions of the ERC721 standard include:
- **balanceOf**: Returns the number of NFTs owned by a given address.
- **ownerOf**: Returns the owner of a specific NFT.
- **transferFrom**: Transfers ownership of an NFT from one address to another.
- **approve**: Approves another address to transfer a specific NFT.
- **setApprovalForAll**: Approves or removes an operator's ability to transfer all of the caller’s NFTs.

### Implementation Details

#### Decentralized Identifiers (DIDs)
In this implementation, each CAV is assigned a unique ERC721 token that serves as its Decentralized Identifier (DID). This token is minted upon the registration of the vehicle and is stored on the blockchain, ensuring immutability and security. The `mint` function of the ERC721 standard is utilized to create these unique tokens:
```solidity
function mint(address to, uint256 tokenId) external {
    _mint(to, tokenId);
}
```
This ensures that each DID is unique and cannot be duplicated, providing a secure method for identifying CAVs.

#### Verifiable Credentials (VCs)
Verifiable Credentials are linked to the DIDs and are stored as metadata within the ERC721 tokens. This metadata can include information such as the vehicle's make, model, year, and other relevant attributes. The `tokenURI` function of ERC721 is used to fetch this metadata:
```solidity
function tokenURI(uint256 tokenId) public view override returns (string memory) {
    return _tokenURIs[tokenId];
}
```
This function ensures that the VCs are easily accessible and verifiable by any party.

#### Authentication and Authorization
The ERC721 standard's built-in functions for ownership and transfer are leveraged to manage authentication and authorization. The `approve` and `setApprovalForAll` functions are used to grant permissions to specific entities, allowing them to perform certain actions on behalf of the vehicle owner:
```solidity
function approve(address to, uint256 tokenId) public override {
    address owner = ERC721.ownerOf(tokenId);
    require(to != owner, "ERC721: approval to current owner");

    require(
        _msgSender() == owner || isApprovedForAll(owner, _msgSender()),
        "ERC721: approve caller is not owner nor approved for all"
    );

    _approve(to, tokenId);
}
```
These functions ensure that only authorized parties can interact with the vehicle's identity data, enhancing security.

### Security Protocols
Security is a critical aspect of this implementation. The immutable nature of the blockchain ensures that DIDs and VCs cannot be altered or tampered with. Additionally, advanced cryptographic techniques such as digital signatures and encryption are employed to protect the integrity and confidentiality of the data.

### Comparison with Other Paradigms
The ERC721-based implementation offers unique advantages in terms of uniqueness and traceability of identities. However, it may have limitations in scalability and flexibility compared to other standards such as ERC725 and ERC1056. This implementation serves as a benchmark to analyze the performance and security of using non-fungible tokens for digital identity management in CAVs.

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
2. Navigate to the ERC721 implementation directory:
   ```bash
   cd CVIN-ID-SCs/ERC721
   ```
3. Install dependencies:
   ```bash
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
