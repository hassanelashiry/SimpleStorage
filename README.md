# SimpleStorage Smart Contract

Welcome to the **SimpleStorage** repository! This project features a Solidity smart contract deployed on the zkSync testnet, utilizing zkSync as a Layer 2 scaling solution for Ethereum. The contract is designed to demonstrate basic storage and retrieval functionalities, manage a list of people, and map names to their favorite numbers.

## Overview

The `SimpleStorage` contract is a straightforward example of how to interact with Ethereum smart contracts on the zkSync network. It includes functionalities to:

- Store and retrieve a single favorite number.
- Maintain a dynamic list of people with their names and favorite numbers.
- Map names to their corresponding favorite numbers.

### Smart Contract Code

Here is the complete Solidity code for the `SimpleStorage` contract:

```solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.24;

contract SimpleStorage {

    uint256 myFavoriteNumber;

    struct Person {
        uint256 favoriteNumber;
        string name;
    }

    Person[] public listOfPeople; // Dynamic array for Person's struct

    mapping (string => uint256) public nameToFavoriteNumber;

    function storeMyFavoriteNumber(uint256 _favoriteNumber) public {
        myFavoriteNumber = _favoriteNumber;
    }

    function retrieve() public view returns (uint256) {
        return myFavoriteNumber;
    }

    function addPerson(string memory _name, uint256 _favoriteNumber) public {
        listOfPeople.push(Person(_favoriteNumber, _name));
        nameToFavoriteNumber[_name] = _favoriteNumber;
    }

}
```

## Deployment

### Environment Setup

1. **Remix IDE**: Use the [Remix IDE](https://remix.ethereum.org/) for Solidity development and deployment.
2. **zkSync Plugin**: Install the zkSync plugin for Remix IDE to enable deployment on the zkSync network.
3. **MetaMask**: Ensure MetaMask is installed and configured to connect with the zkSync test network.

### Deployment Steps

1. **Open Remix IDE**: Navigate to [Remix IDE](https://remix.ethereum.org/).
2. **Install zkSync Plugin**: Access the Remix Plugin Manager and install the zkSync plugin.
3. **Connect MetaMask**: Connect MetaMask to the zkSync test network.
4. **Load Contract Code**: Copy and paste the provided `SimpleStorage` contract code into a new file named `SimpleStorage.sol`.
5. **Compile Contract**: Use Remix IDE to compile the contract with Solidity version `0.8.24`.
6. **Deploy Contract**:
   - Go to the zkSync plugin tab in Remix.
   - Select the compiled contract and deploy it.
   - Confirm the deployment transaction via MetaMask.

## Contract Address

The `SimpleStorage` contract is deployed at the following address on the zkSync testnet:

[0xa6e7e6f3a3f6197Bc358A42587FBa872EdDd3B44](https://sepolia.explorer.zksync.io/address/0xa6e7e6f3a3f6197Bc358A42587FBa872EdDd3B44#contract)

You can view the contract details and interact with it using the zkSync explorer linked above.

## Functions

- **`storeMyFavoriteNumber(uint256 _favoriteNumber)`**: Sets the value of `myFavoriteNumber`.
- **`retrieve()`**: Retrieves the current value of `myFavoriteNumber`.
- **`addPerson(string memory _name, uint256 _favoriteNumber)`**: Adds a new person to the `listOfPeople` array and updates the `nameToFavoriteNumber` mapping.

## Testing

Test the contract functionality using Remix IDE’s testing environment:

1. **Storage Operations**: Ensure that `storeMyFavoriteNumber` and `retrieve` work as expected.
2. **List Management**: Verify that `addPerson` correctly updates the list and mapping.

## Contributing

Contributions to this project are welcome! If you have suggestions, improvements, or find any issues, please open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Feel free to adjust or add any additional information specific to your project or development environment!
