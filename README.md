Here's a README file for your `AstroToken` project:

---

# AstroToken

## Overview
AstroToken is a custom ERC20 token built on the Ethereum blockchain. It features a limited maximum supply, an admin-controlled minting process, and allows users to transfer and burn tokens securely.

This project demonstrates how to implement a custom ERC20 token with additional functionality, such as:
- Enforcing a maximum token supply.
- Restricting minting functionality to the contract admin.
- Allowing all users to transfer and burn their tokens.

## Features
- **Token Name:** AstroToken
- **Symbol:** AST
- **Max Supply:** 100,000 AST
- **Initial Supply:** Defined during contract deployment.
- **Minting:** Only the admin can mint tokens.
- **Burning:** Any user can burn their tokens.
- **Transferring:** Users can transfer tokens freely.

## Smart Contract Details
The contract is implemented using the OpenZeppelin ERC20 standard library, ensuring security and efficiency.

### Functions:
1. **Minting Tokens** (`generateTokens`):
   - Admin-only function to mint new tokens.
   - Ensures that the total supply does not exceed the maximum supply.

2. **Transferring Tokens** (`transferCoins`):
   - Enables users to transfer their tokens to any address.

3. **Burning Tokens** (`destroyTokens`):
   - Allows users to burn (destroy) their tokens, reducing the total supply.

### Events:
- **TokenMinted:** Emitted whenever new tokens are minted.
- **TokenBurned:** Emitted whenever tokens are burned.

## Requirements
- Solidity Version: ^0.8.18
- Node.js and npm
- OpenZeppelin Contracts

## Deployment
1. Clone the repository.
2. Install the required dependencies:
   ```bash
   npm install @openzeppelin/contracts
   ```
3. Deploy the contract using HardHat or Remix:
   - Deploy via HardHat:
     ```bash
     npx hardhat run scripts/deploy.js --network <network_name>
     ```
   - Deploy via Remix:
     - Copy the `AstroToken` contract code to the Remix editor.
     - Compile and deploy the contract.

4. Initialize the contract with the desired initial supply during deployment.

## Interacting with the Contract
### Mint Tokens
Only the admin can mint tokens using the `generateTokens` function:
```solidity
generateTokens(address recipient, uint256 amount);
```

### Transfer Tokens
Any user can transfer tokens using the `transferCoins` function:
```solidity
transferCoins(address to, uint256 amount);
```

### Burn Tokens
Users can burn their own tokens using the `destroyTokens` function:
```solidity
destroyTokens(uint256 amount);
```

## Example Usage
1. Mint 500 tokens to an address (Admin-only):
   ```solidity
   generateTokens(0xRecipientAddress, 500);
   ```

2. Transfer 200 tokens:
   ```solidity
   transferCoins(0xRecipientAddress, 200);
   ```

3. Burn 100 tokens:
   ```solidity
   destroyTokens(100);
   ```

## License
This project is licensed under the MIT License.

---

Let me know if you need additional details or further refinements!
