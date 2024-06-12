# Project Title
Getting Started with Solidity Create a Token
# Description
This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain.We have to fullfill the following reqirements:
1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
2. Your contract will have a mapping of addresses to balances (address => uint)
3.  You will have a mint function that takes two parameters: an address and a value. 
   The function then increases the total supply by that number and increases the balance  of the “sender” address by that amount
 4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
    It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
    and from the balance of the “sender”.
5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
# Getting Started
# Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:

```solidity
    // SPDX-License-Identifier: MIT
    pragma solidity 0.8.18;

    contract MyToken {

        // Public variables
        string public tokenName = "MyToken";
        string public tokenAbbrv = "MTK";
        uint256 public totalSupply;

        // Mapping of addresses to balances
        mapping(address => uint256) public balances;

        // Mint function
        function mint(address _address, uint256 _value) public {
            totalSupply += _value;
            balances[_address] += _value;
        }

        // Burn function
        function burn(address _address, uint256 _value) public {
            require(balances[_address] >= _value, "Balance is too low to burn");
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
 ```

### Compiling the Contract
1. **Select the Compiler**: In the left sidebar, click on the "Solidity Compiler" tab 
2. **Choose Compiler Version**: Select `0.8.18` from the compiler dropdown.
3. **Compile the Contract**: Click the "Compile MyToken.sol" button.
 ### Deploying the Contract
1. **Select the Deploy & Run Transactions Tab**: In the left sidebar, click on the "Deploy & Run Transactions" tab 
2. **Choose Environment**: Select "Remix VM" (or another environment of your choice) from the environment dropdown.
3. **Deploy the Contract**: Make sure `MyToken` is selected in the contract dropdown, then click the "Deploy" button.
 ### Interacting with the Contract
After deployment, the contract will appear under "Deployed Contracts". You can interact with it using the provided UI.

#### Minting Tokens
1. **Locate the mint Function**: In the deployed contract interface, find the `mint` function.
2. **Input Parameters**: Enter the address to mint tokens to and the amount of tokens to mint.
3. **Execute the Function**: Click the `transact` button next to the `mint` function.

#### Burning Tokens
1. **Locate the burn Function**: In the deployed contract interface, find the `burn` function.
2. **Input Parameters**: Enter the address to burn tokens from and the amount of tokens to burn.
3. **Execute the Function**: Click the `transact` button next to the `burn` function.
# Help
Compiler Errors
- **Solution**: Ensure that you have selected the correct compiler version (0.8.18) in the Remix IDE. Also, check for any syntax errors in your Solidity code.

# Authors
sushant10033

sushantraj893@gmail.com
## License
This project is licensed under the MIT License 









