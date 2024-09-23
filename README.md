This repo contains Solidity code of a simple implementation of an ERC-20 token. The token is called **MyTestToken** with a symbol **MTTK**. It follows the ERC-20 standard, allowing basic functionalities like transferring tokens, approving allowances, and querying balances. 

## Token Details

- **Name**: MyTestToken
- **Symbol**: MTTK
- **Decimals**: 0
- **Initial Supply**: 1000 MTTK

Since the token has 0 decimals, each token represents 1 full unit. There are no fractional tokens.

## Features

This contract implements the following ERC-20 functions:

- **`totalSupply()`**: Returns the total token supply.
- **`balanceOf(address account)`**: Returns the token balance of a given account.
- **`transfer(address to, uint256 value)`**: Transfers tokens from the sender to another address.
- **`allowance(address owner, address spender)`**: Returns the remaining tokens that the spender is allowed to transfer on behalf of the owner.
- **`approve(address spender, uint256 value)`**: Sets the allowance for a spender to use the owner's tokens.
- **`transferFrom(address from, address to, uint256 value)`**: Transfers tokens from one account to another, using the allowance mechanism.

## How It Works

1. Upon deployment, the contract creator (the `msg.sender`) is assigned the entire initial supply of 1000 tokens.
2. Users can transfer tokens to others using the `transfer()` function.
3. If someone needs another account to spend tokens on their behalf, they can approve them with `approve()`, which sets an allowance.
4. The approved spender can then use `transferFrom()` to transfer tokens from the owner to another address, respecting the allowed limit.

## Example Usage

- **Transfer tokens**: 
    ```solidity
    token.transfer(0xRecipientAddress, 10);
    ```
- **Approve a spender**: 
    ```solidity
    token.approve(0xSpenderAddress, 50);
    ```
- **Transfer tokens on behalf of someone**: 
    ```solidity
    token.transferFrom(0xOwnerAddress, 0xRecipientAddress, 20);
    ```

## Error Handling

- **Insufficient balance**: If you try to transfer or spend more tokens than available, the transaction will revert.
- **Invalid address**: Transfers or approvals to the zero address (`0x0`) are not allowed and will revert.
- **Allowance exceeded**: If a spender tries to transfer more than their allowance, the transaction will revert.

## Installation

1. Clone the repository and install dependencies.
2. Deploy the contract to an Ethereum-compatible blockchain using a platform like [Remix](https://remix.ethereum.org/) or [Hardhat](https://hardhat.org/).

## License

This project is licensed under the MIT License - see the LICENSE file for details.

---

This README provides a clear and concise overview of the project. You can customize it further as needed!
