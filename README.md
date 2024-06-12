
# Project Title

Getting Started with Solidity
Project: Create a Token

## Description

In this project, we will create a Solidity contract that fulfills the following requirements:

 1. The contract will have public variables that store the details about your coin (Token Name, Token Abbreviation, Total Supply).
 2. The contract will have a mapping of addresses to balances (address => uint).
 3. It will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the specified address by that amount.
 4. The contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint function. It will then deduct the value from the total supply and from the balance of the specified address.
 5. The burn function will have conditionals to ensure the balance of the account is greater than or equal to the amount that is supposed to be burned.

## Getting Started
### Installing

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Instructions
1. Create a New File:
  Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar.
  Save the file with a .sol extension (e.g., mytoken.sol).
  Copy and paste the following code into the file:

```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {
    // Public variables to store details about the token
    string public tokenName = "IrisCoin"; 
    string public tokenAbbrv = "Iris"; 
    uint public totalSupply = 0; 

    // Mapping of addresses to balances
    mapping(address => uint) public balances; 
    // mapping  datastructure is used to keep track of the balance of each address. 
    // When an address is provided, it returns the amount of tokens the address has.

    // Mint function to create new tokens
    function mint(address _address, uint _value) public {
        totalSupply += _value; 
        balances[_address] += _value; 
    }

    // Burn function to destroy tokens
    function burn(address _address, uint _value) public {
        // To check if address has enough balance to burn the specified amount of tokens.
        if (balances[_address] >= _value) {
            totalSupply -= _value; 
            balances[_address] -= _value; 
        }
    }
}

```

2. Compile the Code:
   
        Click on the "Solidity Compiler" tab in the left-hand sidebar.

        Ensure the "Compiler" option is set to "0.8.18" (or another compatible version).
  
        Click the "Compile mytoken.sol" button.
  
3.Deploy the Contract:

         After the code is compiled, click on the "Deploy & Run Transactions" tab in the left-hand sidebar.
  
        Select the MyToken contract from the dropdown menu.
  
        Click on the "Deploy" button.
  
4.Interact with the Contract:

      Once the contract is deployed, you will see it listed under "Deployed Contracts" at the bottom of the sidebar.
  
      Expand the deployed contract to see available functions such as balances, mint, and burn.
    
      You can now interact with your contract by calling these functions.



## Authors

Contributors names and contact info

Abhishek

email : abhishekpawan6317@gmail.com

## License
This project is licensed under the MIT License - see the LICENSE.md file for details
