# Private Blockchain with GETH
This project demonstrates how to create a private blockchain using GETH, a command-line interface for running Ethereum nodes. By following the instructions below, you'll be able to set up your own private Ethereum network and interact with it using the GETH console.

Getting Started
To get started with this project, follow these steps:

Install GETH on your computer by following the instructions in the official documentation.

Clone this repository to your local machine.

In a terminal window, navigate to the root directory of the project and run the following command to initialize a new blockchain:

`geth --datadir=./data init ./genesis.json`
This will create a new blockchain database in the ./data directory, based on the configuration specified in the ./genesis.json file.

Start a new GETH node by running the following command:


`geth --datadir=./data --networkid=1234 --port=30303 --rpc --rpcaddr=0.0.0.0 --rpcport=8545 --rpcapi="db,eth,net,web3,personal`,miner" console
This will start a new GETH node with the following options:

--datadir=./data: specifies the data directory for the blockchain database.
--networkid=1234: specifies the network ID for the private network. You can choose any number here, but it must be unique to your network.
--port=30303: specifies the P2P port for the GETH node.
--rpc: enables the JSON-RPC API for the GETH node.
--rpcaddr=0.0.0.0: specifies the IP address for the JSON-RPC API. Setting this to 0.0.0.0 allows any computer on the network to access the API.
--rpcport=8545: specifies the port for the JSON-RPC API.
--rpcapi="db,eth,net,web3,personal,miner": specifies the APIs that should be enabled for the JSON-RPC API. This list includes the APIs needed to interact with the blockchain using GETH.
console: starts the GETH console after the node is initialized.
In a separate terminal window, navigate to the root directory of the project and run the following command to connect to the GETH console:


geth attach http://localhost:8545
This will connect to the GETH console running on localhost:8545.

You can now interact with the private blockchain using the GETH console commands. For example, you can create a new account by running the following command in the console:

personal.newAccount()
This will prompt you to enter a passphrase for the new account, and will then create the account and return its address.
