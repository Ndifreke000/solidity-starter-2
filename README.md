Contract Overview
This Solidity contract implements a simple assessment system with two main functions: deposit and withdraw. It allows a designated owner to track the contract's balance and manage funds through deposits and withdrawals.

Pragma Directive
Solidity
pragma solidity ^0.8.9;
Use code with caution. Learn more
This line specifies the compatible Solidity compiler versions for this contract.

Contract Declaration
Solidity
contract Assessment { ... }
Use code with caution. Learn more
This line defines the contract itself, named "Assessment". All contract functionalities and variables are enclosed within this block.

State Variables
address payable public owner: This variable stores the address of the contract owner. It is public, meaning its value can be read from the blockchain by anyone. It is also payable, meaning it can receive funds.
uint256 public balance: This variable stores the current balance of the contract. It is also public and accessible to everyone.
Events
event Deposit(uint256 amount): This event is emitted whenever a deposit occurs in the contract. It logs the deposited amount for transparency.
event Withdraw(uint256 amount): This event is emitted whenever a withdrawal occurs in the contract. It logs the withdrawn amount for transparency.
Constructor
Solidity
constructor(uint256 initBalance) payable { ... }
Use code with caution. Learn more
This function is called upon contract deployment. It initializes the owner address and sets the initial balance of the contract. The constructor can receive initial funds through the payable keyword.

View Function
Solidity
function getBalance() public view returns (uint256) { ... }
Use code with caution. Learn more
This function allows anyone to retrieve the current balance of the contract without modifying any state variables. It is marked as public and view for accessibility and gas efficiency.

Deposit Function
Solidity
function deposit(uint256 _amount) public payable { ... }
Use code with caution. Learn more
This function allows the contract owner to deposit funds into the contract. It takes a parameter _amount specifying the amount to deposit. Only the owner can call this function.

Custom Error
Solidity
error InsufficientBalance(uint256 balance, uint256 withdrawAmount);
Use code with caution. Learn more
This custom error is defined to handle situations where the withdrawal amount exceeds the contract's current balance.

Withdraw Function
Solidity
function withdraw(uint256 _withdrawAmount) public { ... }
Use code with caution. Learn more
This function allows the contract owner to withdraw funds from the contract. It takes a parameter _withdrawAmount specifying the amount to withdraw. The function checks for sufficient balance and throws a custom error if the withdrawal amount is greater than the balance.

Functionality Summary
The contract allows depositing and withdrawing funds by the owner.
The contract's balance and deposit/withdrawal events are visible on the front-end.
A custom error ensures secure transactions by preventing withdrawal beyond the available balance.
