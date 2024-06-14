# MetaCraftersSOL Token Contract

MetaCraftersSOL is a Solidity smart contract that implements a simple ERC-20-like token with minting and burning functionalities. This project demonstrates basic token management on the Ethereum blockchain.

## Description

This Solidity contract, named `MyToken`, stores details about a custom token named "Meta" with the abbreviation "MTA". The contract allows for minting new tokens to increase the total supply and burning tokens to decrease the total supply. Each account's balance is tracked using a mapping.

## Getting Started

### Executing Program

To run this program, you can use [Remix](https://remix.ethereum.org/), an online Solidity IDE.

#### Steps

1. **Open Remix**: Go to the [Remix website](https://remix.ethereum.org/).
2. **Create a New File**: Click on the "+" icon in the left-hand sidebar. Save the file with a `.sol` extension (e.g., `MyToken.sol`).
3. **Copy and Paste Code**: Copy and paste the following code into the new file:

    ```solidity
    // SPDX-License-Identifier: MIT
    pragma solidity >=0.6.12 <0.9.0;

    contract MyToken {

        // public variables here
        string public tokenName = "Meta";
        string public tokenAbb = "MTA";
        uint public totalSup = 0;

        // mapping variable here
       mapping(address => uint) public balances;
       
        // mint function
       function mint(address _address, uint _value) public {
          totalSup += _value;
          balances[_address] += _value;
       }
        // burn function
       function burn(address _address, uint _value) public {
          if(balances[_address] >= _value){
          totalSup -= _value;
          balances[_address] -= _value;
          }
       }
    }
    ```

4. **Compile the Code**:
    - Click on the "Solidity Compiler" tab in the left-hand sidebar.
    - Make sure the "Compiler" option is set to a compatible version (e.g., `0.6.12` to `0.9.0`).
    - Click on the "Compile MyToken.sol" button.

5. **Deploy the Contract**:
    - Click on the "Deploy & Run Transactions" tab in the left-hand sidebar.
    - Select the "MyToken" contract from the dropdown menu.
    - Click on the "Deploy" button.

6. **Interact with the Contract**:
    - After deployment, click on the "MyToken" contract in the left-hand sidebar.
    - You can now call the `mint` and `burn` functions to manage the token supply.
        - **Mint Tokens**: Call `mint(address _address, uint _value)` with the desired address and token amount.
        - **Burn Tokens**: Call `burn(address _address, uint _value)` with the desired address and token amount (ensure the address has enough tokens to burn).

## Features

- **Token Details**: Public variables for token name, abbreviation, and total supply.
- **Minting**: Function to mint new tokens, increasing total supply and the balance of the specified address.
- **Burning**: Function to burn tokens, decreasing total supply and the balance of the specified address, with balance checks.

## Authors

- **Metacrafter Bryce**
    - Twitter: [@Mhistwy](https://twitter.com/Mhistwy)

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
