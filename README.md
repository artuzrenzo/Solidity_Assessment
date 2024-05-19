# MyToken
In this Solidity program, you can mint, burn, check your token balance, and view your current token supply. 

# Description
Using Solidity, we can develop smart contracts for the Ethereum blockchain using this simple contract. With this contract, the user has the ability to create tokens (mint), destroy tokens (burn), check your token balance under your address, and determine the current token supply. 
# Getting Started
### Executing program 
The program can be run using Remix, an online Solidity IDE. Get started by visiting https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:
```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.25;
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
    function mint (address _address, uint _value) public {
      totalSupply += _value;
      balances[_address] += _value;
    }
    // burn function
    function burn (address _address, uint _value) public {
      if (balances[_address] >= _value) {
      totalSupply -= _value;
      balances[_address] -= _value;
      }
    }
}
```
Compiling the code is accomplished by clicking on the "Solidity Compiler" tab on the left-hand sidebar. Click on the "Compile Name_Token.sol" button, and ensure the "Compiler" option is set to "0.8.25" (or another compatible version).

The contract can be deployed once the code has been compiled by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. By selecting "MyToken - Name_Token.sol" in the drop-down menu, then clicking "Deploy", the contract will be deployed.

When the contract has been deployed, you are able to interact with it by calling the functions mint, burn, tokenAbbrv, tokenName, and totalSupply. The first thing I would like you to do is find your address. To do this find the "account" under "Deploy and run transactions" and then copy the address that has an unlimited amount of tokens. In the "Deployed Contracts" section, check the "totalSupply" function first to determine whether our token supply has been set at zero. As with the "balance" function, the totalSupply function also requires an account address. For our next step, we will call the Mint function, and we will paste our account address and the value of the token we wish to mint. Let's say we wish to mint at least 1000 tokens. We now have 1000 tokens. Simply go to the totalSupply or balance functions to verify this. As soon as the Burn function is called, tokens will be deducted from the address. Let us say we wish to remove 500 tokens from the same address. First paste the address into the address box, then type 500 in the value box, and lastly call the tokenSupply or Balance function to determine if it worked.


This is a brief summary of my simple contract for handling MyTokens. 

# Author
+ NTC PH Renzo D. Artuz
+ @metacraftersio

# License
This project is licensed under the MIT License - see the LICENSE.md file for details
