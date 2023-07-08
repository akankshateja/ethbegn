# ethbegn creating a token
The program introduces "MyToken," a straightforward custom token built with Solidity on the Ethereum blockchain. 
Tokens can be created and destroyed while individual balances and the total supply are tracked. 
With the capacity to mint new tokens and consume existing ones, the program guarantees that symbolic holders have sufficient equilibrium prior to playing out any consuming activities.
By sticking to the MIT permit, this agreement can be uninhibitedly utilized and circulated. 
It offers a dependable solution for token issuance and tracking and provides a user-friendly and accessible framework for creating and managing custom tokens on the Ethereum platform.
## Description
"MyToken" for the Ethereum blockchain, written in Solidity. The agreement incorporates public factors to store fundamental subtleties of the token, like its name, truncation, and absolute stockpile. 
It connects Ethereum addresses to their respective token balances through a mapping known as "tokenHolders," making it possible to effectively track and manage ownership. 
There are two main functions provided by the program: burn" and "mint." The "mint" function makes it possible to create new tokens, increase the total supply, and update the recipient address's balance.
The "consume" capability works with the obliteration of tokens, lessening the all out supply and deducting the predefined sum from the symbolic holder's equilibrium. 
Importantly, there is a check built into the "burn" function to make sure that the token holder's balance is enough to cover the burn amount that was requested.
The contract is a complete solution for token creation, destruction, and balance management in a safe and decentralized blockchain environment thanks to these features.

## Getting Started

### Installing
Copy the code and paste it in remix ide.

### Executing program
First deploy the program. After that we can use the default address provided. Paste the address in the mint add the value Check the Balance. Also we can burn the token via burn. Add the address. Burn the token. Check the balance.

```
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
    string public tokenName="META";
    string public tokenAbbrv="MTA";
    uint public totalSupply=0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address,uint _value) public{
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address,uint _value) public{
        if(balances[_address]>=_value){
        totalSupply -= _value;
        balances[_address] -= _value;
        }
    }    

}
```


## Authors
Akanksha Teja


