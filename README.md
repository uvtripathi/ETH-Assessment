# MyToken (Solidity Contract)

## Description
MyToken is a simple ERC20-like token contract implemented in Solidity. It allows minting of tokens to addresses and burning of tokens from addresses, while maintaining balances and total supply.

## contract code
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // Public variables
    string public Token_name = "yuvi";
    string public Token_Abbrv = "yu";
    uint public totalSupply;

    // Mapping of addresses to balances
    mapping(address => uint) public balances;

    // Mint function
    function mint(address _to, uint _value) public {
        totalSupply += _value;
        balances[_to] += _value;
    }

    // Burn function
    function burn(address _from, uint _value) public {
        require(balances[_from] >= _value, "Insufficient balance");
        totalSupply -= _value;
        balances[_from] -= _value;
    }
}
## Contract details
1. The contract has public variables that store details about the token:
   - `Token_name`: Name of the token (e.g., "yuvi").
   - `Token_Abbrv`: Abbreviation of the token (e.g., "yu").
   - `totalSupply`: Total supply of the token.

2. A mapping of addresses to token balances (`balances`).

3. `mint` function:
   - Takes two parameters: `_to` (address to mint tokens to) and `_value` (amount of tokens to mint).
   - Increases the total supply by `_value`.
   - Increases the balance of `_to` address by `_value`.

4. `burn` function:
   - Takes two parameters: `_from` (address to burn tokens from) and `_value` (amount of tokens to burn).
   - Checks if the balance of `_from` is sufficient to burn `_value` tokens.
   - Decreases the total supply by `_value`.
   - Decreases the balance of `_from` address by `_value`.
   - Includes conditionals to ensure the balance of `_from` is greater than or equal to `_value`.



## Usage
. Deploy the contract on a compatible Ethereum Virtual Machine (EVM) using a Solidity compiler. Or
You run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

2. Interact with the contract through transactions:
   - Use the `mint` function to create tokens for specific addresses.
   - Use the `burn` function to destroy tokens from specific addresses.
   - Retrieve token balances using the `balances` mapping.
   - Retrieve total supply using the `totalSupply` variable.

## Authors

uvtripathi  (tripathiyuvraj56@gmail.com)
