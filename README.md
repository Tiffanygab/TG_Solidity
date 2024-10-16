# MyToken Smart Contract

## Create a Token

 This Solidity program demonstrates how basic minting and burning of tokens works using Solidity on the Ethereum blockchain. The purpose of this program is to introduce basic token management functions, providing an easy-to-understand foundation for more complex blockchain projects in the future.

## Description
 This contract is a simple implementation written in Solidity, a programming language for smart contracts on the Ethereum blockchain. The contract includes two key functions: mint, which allows the creation of tokens, and burn, which allows the destruction of tokens. The contract tracks the total supply of tokens and the balance of tokens for each user.

## Getting Started
#### Executing the Program
 To run this program, you can use Remix, an online Solidity IDE. To get started, follow these steps:
#### Open the Remix IDE at https://remix.ethereum.org.
 In the left-hand sidebar, click the "+" button to create a new file. Save the file with a .sol extension (e.g., MyToken.sol).
Copy and paste the following Solidity code into the new file:

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // Public variables
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // Mapping to store token balances
    mapping(address => uint) public balances;

    // Mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // Burn function
    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient tokens to burn");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}

Go to the "Solidity Compiler" tab in the left-hand sidebar. Make sure the compiler version is set to 0.8.18 (or another compatible version), then click "Compile MyToken.sol.

After compiling, navigate to the "Deploy & Run Transactions" tab. From the dropdown, choose the MyToken contract and click "Deploy."

Once the contract is deployed, you can interact with it. Use the mint function to add tokens to an address and the burn function to remove tokens. Simply enter the address and the number of tokens to mint or burn, then click "transact."

## Author
Tiffany Kyla S. Gabriel | 202110672@fit.edu.ph

## License
This project is licensed under the MIT License


