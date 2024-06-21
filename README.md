# Tokens Creation

This Solidity program is program that demonstrates how tokens can be created using Solidity, how the functionalities of Solidity works and how can we implement them to create smart contracts.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. In the contract we need to have:
1. Public variables for Token Name, Token Abbrv, and Total Supply.
2. Mapping of addresses to balances using address => uint.
3. The mint function that increases the total supply and the balance of a specific address.
4. The burn function that decreases the total supply and the balance of a specific address.
5. Implementing conditionals in the burn function to ensure the balance of the account is greater than or equal to the amount being burned. 

## Getting Started

### Executing program

To run this program, we are using Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., createTokens.sol). Copy and paste the basic syntax provided:

```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

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

    // mapping variable here

    // mint function

    // burn function

}

```
You can meet the necessary requirements mentioned as shown below or can make it run as per you desire:
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

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
    string public tokenName = "Cello";
    string public tokenAbb = "CLO";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _addr, uint _value) public {
        totalSupply += _value;
        balances[_addr] += _value;

    }
    // burn function
    function burn (address _addr, uint _value) public {
        if (balances[_addr] >= _value)
        {
            totalSupply -= _value;
            balances[_addr] -= _value;
        }
    }
}
```
To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.18", and then click on the "Compile createTokens.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "createTokens" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by copying the account, pasting it in the mint function's address, providing the value and clicking the transact button. After the transaction has processed, one can see changes in the "totalSupply" and "balances". Trying doing the same with the burn function and observe the changes.
## Authors

Aditi Tiwari
www.linkedin.com/in/aditi-tiwari-790827230
