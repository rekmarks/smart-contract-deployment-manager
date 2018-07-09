# smart-contract-deployment-manager
For programmatically deploying an arbitrary number of pre-compiled smart contracts

## usage

Import the package to access the `Deployer` class, which by default supports an OpenZeppelin-based ERC20 token contract, `StandardERC20`.
- instantiate a deployer using `Deployer(web3Provider, accountAddress, gasLimit)`
- add a contract type to deploy instances of it using `deployer.addContract(compiledJSON)`
    - `compiledJSON` must be an undeployed, compiled Truffle artifact, i.e. the output of `truffle compile`
- deploy and access a deployed contract instance using `const instance = deployer.deploy(contractName, constructorParameters)`
    - contractName must be `StandardERC20` or the name of a contract added using `addContract`
- consult `src/deployer.js` for additional methods you may want
