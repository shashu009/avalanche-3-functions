# Token 

This repository contains a Solidity smart contract implementing a basic ERC-20 token with additional functionalities. The contract is designed to be deployed on the Ethereum blockchain and utilizes the OpenZeppelin library for ERC-20 implementation and access control through Ownable.

## Contract Overview

### ERC-20 Token Standard

The `Token` contract extends the OpenZeppelin ERC20 contract, providing standard ERC-20 token functionalities such as minting, burning, and transferring tokens. The contract includes events to log token transfers and allowance changes.

### Ownable

The contract utilizes the Ownable contract from OpenZeppelin, ensuring that only the owner (deployer) of the contract has certain privileged functions, enhancing security and control.

## Contract Features

1. **Token Initialization:**
   - The contract is initialized with a title, symbol, and an initial supply of tokens.
   - The constructor function takes three parameters: `title` (string), `symbol` (string), and `initialSupply` (uint256).

2. **Mint Function:**
   - The owner can mint new tokens and transfer them to a specified address.
   - Function: `mintFunction(address successor, uint256 issuedAmount) external onlyOwner`

3. **Burn Function:**
   - Token holders can burn their own tokens, reducing the total supply.
   - Function: `burnFunction(uint256 destroyedAmount) external`

4. **Transfer Function:**
   - Token holders can transfer tokens to another address.
   - Function: `transferFunction(address successor, uint256 transferAmount) external`

5. **Set Allowance Function:**
   - The owner can set allowances for a spender to spend tokens on behalf of the owner.
   - Function: `setAllowance(address spender, uint256 allowanceAmount) external onlyOwner`

## Events

1. **TokensTransferred:**
   - Logs token transfers, including sender, successor, and the transferred amount.

   ```solidity
   event TokensTransferred(address indexed sender, address indexed successor, uint256 amount);
   ```

2. **AllowanceSet:**
   - Logs changes in allowances, including owner, spender, and the allowance amount.

   ```solidity
   event AllowanceSet(address indexed owner, address indexed spender, uint256 allowance);
   ```

## Usage

1. **Deployment:**
   - Deploy the contract on the Ethereum blockchain by providing the required parameters in the constructor.

2. **Interaction:**
   - Interact with the contract using a Ethereum-compatible wallet or through a DApp.
   - Use the provided functions to mint, burn, transfer tokens, and set allowances.

3. **Access Control:**
   - Only the owner can execute certain functions (as specified by the Ownable contract), providing control over critical contract operations.

## Example Deployment

```solidity
Token myToken = new Token("My Token", "MTK", 1000000);
```

This deploys the contract with the title "My Token," symbol "MTK," and an initial supply of 1,000,000 tokens.

## Contributors

- [Shashank S R]

## License

This contract is released under the MIT License. See the [LICENSE](LICENSE) file for details.
