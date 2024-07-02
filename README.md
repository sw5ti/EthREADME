# Customizable Solidity Token Contract

This Solidity contract provides a foundational framework for creating your own token with customizable attributes like name, abbreviation, and total supply. It implements essential functions for minting and burning tokens, allowing you to manage token distribution within your decentralized application.

## Description

SimpleCoin offers a straightforward and adaptable smart contract that can be tailored to your specific token requirements. It defines public variables for the token's name, abbreviation, and total supply. A mapping tracks individual account balances. The contract includes functions for minting new tokens (increasing total supply and assigning them to an address) and burning existing tokens (reducing total supply and deducting them from an address). Burn functionality incorporates essential checks to ensure sufficient balance before burning.

## Getting Started

### Installing

* Open Remix IDE: Navigate to https://remix.ethereum.org/ in your web browser.
* Create a New File: Click on the "+" symbol in the file explorer on the left side of the Remix IDE interface. Choose "File" and name it SimpleCoin.sol. Paste the provided Solidity contract code into this file.
* Select Solidity Version: In the top right corner of the Remix IDE, you'll see a dropdown menu for the Solidity compiler version. Ensure it's set to a compatible version for your code (e.g., 0.8.18 if the code uses pragma solidity 0.8.18;).

### Executing program

* Compile the Contract: Click on the "Compile" button (play icon) in the top right corner of the Remix IDE. This will compile the SimpleCoin.sol contract and check for any syntax errors.
* Deploy the Contract: While Remix allows deployment to test networks, it's recommended to test your contract thoroughly in a local development environment before deploying to a public network. For testing purposes within Remix, you can use the "Deploy" button in the top right corner. However, for production use, consider setting up a local blockchain environment (e.g., with tools like Ganache) for more robust testing.
* Interact with the Contract: Once compiled, you can interact with the SimpleCoin contract functions directly in the Remix IDE. Expand the "Deploy" tab and locate the SimpleCoin contract instance. You can call functions like mint and burn by providing the necessary arguments (address, value) and clicking the "transact" button. The Remix IDE will display the transaction details and update the contract state after a successful execution.
code blocks for commands
```
  // SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
contract MyToken {

    // public variables here
      string public tokenName = "META";
      string public tokenAbbrv = "MTA";
      uint public totalSupply = 0;

    // mapping variable here
      mapping(address => uint) public balances;
      
    // mint function
      function mint (address _address, uint _value) public{
         totalSupply += _value;
         balances[_address] += _value;
      }

    // burn function
      function burn (address _address, uint _value)public{
         if(balances[_address] >= _value){
         totalSupply -= _value;
         balances[_address] -= _value;
         }
      }
}
```

## Authors

Swati Kumari
[@SWATI](swaditya.sk54@gmail.com)

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
