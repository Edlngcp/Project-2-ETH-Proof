# Create A Token

Smart Contract Token for Decentralized Applications

This project involves the creation of a smart contract written in Solidity that governs the issuance, minting, and burning of a custom ERC-20-like token. It demonstrates basic token management operations, such as adding to the total supply (minting) and removing from the total supply (burning), while keeping track of token balances for different users.


## Description

This smart contract allows users to create, manage, and interact with a custom cryptocurrency token. It includes features to mint new tokens, adding them to the total supply and the specific user's balance, and a burn mechanism to destroy tokens and reduce both the total supply and the user’s balance. The contract employs Solidity's mappings to track balances of token holders and ensures proper conditions before allowing token burning. This example is perfect for understanding the basic functions of a token contract in a decentralized finance (DeFi) or blockchain-based system, laying the foundation for more complex functionalities like transfers, staking, or governance.

The token name is META, with an abbreviation MTA, and it starts with a total supply of 0, which will increase or decrease based on minting and burning operations. The contract also enforces security checks to prevent users from burning more tokens than they possess.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., HelloWorld.sol). Copy and paste the following code into the file:

```Solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.18;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // public variables here
    string public tokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value)public {
        totalSupply += _value;
        balances[_address] += _value;
    }
    // burn function
    function burn (address _address, uint _value)public {
        if(balances[_address] >= _value){
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }

}
```

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile HelloWorld.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "HelloWorld" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the sayHello function. Click on the "HelloWorld" contract in the left-hand sidebar, and then click on the "sayHello" function. Finally, click on the "transact" button to execute the function and retrieve the "Hello World!" message.

## Authors
Eddie Longcop

Metecrafter Toky0
