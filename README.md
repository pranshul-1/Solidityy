Token Creator: 
  Simple solidity smart contract to create a token and transact with it.
  
Description:
  In this smart contract, I created my Token "Lazer Coin" with abbrevation "LC" and total supply as 10 intially.
  I can mint or burn LC in my wallet providing address and value of LC to be minted or burned using mint and burn functions as specified format.
  
Getting Started:
  To run this contract, simply go to Remix website - https://remix.ethereum.org/
  Then create a new file in contracts folder with .sol extenstion,
  Then copy the code below and paste it in the solidity file,

    // SPDX-License-Identifier: GPL-3.0
    pragma solidity ^0.8.7;
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

    contract MineToken {

        // public variables here
        string public tokenName = "Lazer Coin";
        string public tokenAbbrv = "LC";
        uint public totalSupply = 10;

        // mapping variable here
        mapping (address => uint) public balances;

        // mint function
        function mint(address adrs, uint value) public{
            totalSupply +=value;
            balances[adrs] +=value;
        }
        // burn function
        function burn(address adrs, uint value) public{
            if(balances[adrs] >=value){
                totalSupply -=value;
                balances[adrs] -=value;
            }
        }
    }

  Then compile the contract using ctrl + S or in the compiler menu,
  Then in deploy tab, Click on Deploy,
  Finally when contract is deployed, you can perform transaction and check for total supplies.
  
Authors:
Pranshul Pal
@pranshul-1
