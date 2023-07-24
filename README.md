# AVAX_TYPYEV_OF_FUNCTION3
External Functions:

External functions are the most common type of functions in smart contracts on the Avalanche blockchain.
They can be called externally by other contracts or accounts.
When an external function is called, it consumes gas, and its execution is visible to all nodes on the network.
External functions are usually used for actions that modify the state of the contract, such as transferring tokens, updating data, or performing other contract-specific operations.
View and Pure Functions:

View and pure functions are read-only functions that do not modify the state of the contract.
View functions are used to retrieve data from the contract's state, and they don't consume gas when called.
Pure functions are used for computations based solely on their input parameters, and they don't interact with the contract state or consume gas.
View and pure functions are useful for fetching information from the blockchain without incurring any transaction costs.
In the Avalanche blockchain, just like in other EVM-compatible blockchains (such as Ethereum), contracts are written in Solidity or other compatible programming languages. The type of function (external, view, or pure) is specified in the contract code using specific keywords like external, view, and pure.


Set Up the Project:

Create a new directory for your project.
Initialize a new npm project and install the necessary 
npm init -y
npm install hardhat @openzeppelin/contracts --save-dev




Create a new file named deploy.js in your project directory.
Add the following content to the deploy.js file:

follow this code........


const hre = require("hardhat");

async function main() {
  const Token = await hre.ethers.getContractFactory("Token");
  const token = await Token.deploy("MyToken", "MTK"); // Provide your desired name and symbol here
  await token.deployed();

  console.log("Token deployed to:", token.address);
}

main()
  .then(() => process.exit(0))
  .catch((error) => {
    console.error(error);
    process.exit(1);
  });
