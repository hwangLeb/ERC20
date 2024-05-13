# ERC20
ERC-20 (Ethereum Request for Comment 20) is a technical standard for smart contracts on the Ethereum blockchain. ERC-20 is a standard that describes how the given tokens designed to be used on Ethereum should interact and this standard defines a set of rules and functions that all those interpretations must follow to be considered as ERC-20 compliant. These rules cover how to transfer tokens from one wallet to another, display the total number of tokens in circulation, discover the balance of tokens for an Ethereum account, and many other related processes. ERC-20 tokens have become the dominant type of tokens on the Ethereum network for conducting initial coin offerings (ICOs) and implementing various decentralized applications (DApps). Creation of standard ERC-20 tokens offers simplicity to developers who can build interchangeable tokens for the platforms and enable users to transact with universal wallets and exchanges which are ERC-20 compliant.

# GETTING STARTED
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., LeviToken.sol). Copy and paste the following code into the file:

// SPDX-License-Identifier: UNLICENSED
pragma solidity ^0.8.0;

import "@openzeppelin/contracts/token/ERC20/ERC20.sol";

contract LEVI is ERC20 {
    address public owner;

    constructor(string memory name, string memory symbol) ERC20(name, symbol) {
        owner = msg.sender;
    }

    modifier Owner() {
        require(msg.sender == owner, "Only the owner can call this function");
        _;
    }

    function mint(address to, uint256 amount) external Owner {
        _mint(to, amount);
    }

    function burn(uint256 amount) external {
        _burn(msg.sender, amount);
    }
}

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.0" (or another compatible version), and then click on the "Compile LeviToken.sol" button.

Once the code is compiled, go to "Deploy and run transactions" then you will see the contract, just select the "LeviToken.sol" then click the deploy button.

Before you deploy the contract, you need to input first the name and symbol of your token. After that, you can now use the function mint, burn and transact. For transact, you a copy of account address of being passed on.

# AUTHOR
Eugenio, Viel
3.1 BSIT
