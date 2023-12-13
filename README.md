# Assessment Smart Contract

## Contract Overview

This Solidity contract implements a simple assessment system with two main functions: deposit and withdraw. It allows a designated owner to track the contract's balance and manage funds through deposits and withdrawals.

## Pragma Directive

```solidity
pragma solidity ^0.8.9;
```

This line specifies the compatible Solidity compiler versions for this contract.

## Contract Declaration

```solidity
contract Assessment { ... }
```

This line defines the contract itself, named "Assessment." All contract functionalities and variables are enclosed within this block.

## State Variables

- `address payable public owner`: This variable stores the address of the contract owner. It is public, meaning its value can be read from the blockchain by anyone. It is also payable, meaning it can receive funds.
- `uint256 public balance`: This variable stores the current balance of the contract. It is also public and accessible to everyone.

## Events

- `event Deposit(uint256 amount)`: This event is emitted whenever a deposit occurs in the contract. It logs the deposited amount for transparency.
- `event Withdraw(uint256 amount)`: This event is emitted whenever a withdrawal occurs in the contract. It logs the withdrawn amount for transparency.

## Constructor

```solidity
constructor(uint256 initBalance) payable { ... }
```

This function is called upon contract deployment. It initializes the owner address and sets the initial balance of the contract. The constructor can receive initial funds through the payable keyword.

## View Function

```solidity
function getBalance() public view returns (uint256) { ... }
```

This function allows anyone to retrieve the current balance of the contract without modifying any state variables. It is marked as public and view for accessibility and gas efficiency.

## Deposit Function

```solidity
function deposit(uint256 _amount) public payable { ... }
```

This function allows the contract owner to deposit funds into the contract. It takes a parameter _amount specifying the amount to deposit. Only the owner can call this function.

## Custom Error

```solidity
error InsufficientBalance(uint256 balance, uint256 withdrawAmount);
```

This custom error is defined to handle situations where the withdrawal amount exceeds the contract's current balance.

## Withdraw Function

```solidity
function withdraw(uint256 _withdrawAmount) public { ... }
```

This function allows the contract owner to withdraw funds from the contract. It takes a parameter _withdrawAmount specifying the amount to withdraw. The function checks for sufficient balance and throws a custom error if the withdrawal amount is greater than the balance.

## Functionality Summary

- The contract allows depositing and withdrawing funds by the owner.
- The contract's balance and deposit/withdrawal events are visible on the front-end.
- A custom error ensures secure transactions by preventing withdrawal beyond the available balance.

