# Instructions

## Create Nodes

![create_node_1](Screenshots/create_node1_code.png)

Node1 is created along with its private and public keys:
![create_node_1_response](Screenshots/create_node1_response.png)



![create_node_2](Screenshots/create_node2_code.png)

Node2 is created along with its private and public keys:
![create_node_2_response](Screenshots/create_node2_response.png)

It's generally a good idea to save node keys in a text file.  The keys can also be found in the node's 'keystore' folder.
![keystore](Screenshots/node1_keystore_contents.png)

## Create Genesis Block and Network

Run puppeth in terminal:

![puppeth](Screenshots/puppeth_start.png)

![new genesis](Screenshots/puppeth_configure_new_genesis.png)

Choose a name for your new network.  In the above situation, there is an existing genesis.  Otherwise, option 2 is replaced with "Configure new genesis from scratch.  Select 'manage existing genesis', remove it, then configure a new genesis.  For this exercise, we are using proof of authority.


![genesis config continued](Screenshots/puppeth_config2.png)

Provide the node addresses for accounts that are allowed to seal query.  Both of these addresses should also be designated for pre-funding.  You can enter a specific number for the chain ID or have it default to a random number.

Run puppeth again and choose 'Manage existing genesis'.  This is the genesis block you just created.  Then select 'Export existing genesis'

![export genesis](Screenshots/puppeth_export_genesis_config.png)

This action creates .json files.  You will need the [your-network-name].json file to initial the nodes in the next step.

## Initialize Nodes

Initialize node 1:

![node_1 init](Screenshots/node1_initialize.png)

The following log is returned:

![node_1 init log](Screenshots/node1_initialize_response.png)


Initialize node 2:

![node_2](Screenshots/node2_initialize.png)

The following log is returned:

![node_2 log](Screenshots/node2_initialize_response.png)

Note that the genesis network .json file is passed through as a parameter of the init command.


## Run Nodes (Proof of Authority)

Run node 1:

![node_1 run](Screenshots/node1_run.png)

The following log is created:

![node_1 run log](Screenshots/node1_run_response.png)

While the log is running, make sure to enter the password set up when creating the node.  This will unlock the account.

![node_1_unlock](Screenshots/node_account_unlocked_confirm.png)

Run node 2:

![node_2](Screenshots/node2_run.png)

Note that you will need to enter the enode address of node1 after --bootnodes.  This allows node 2 to find node1 as a peer in the network.  As with node 1, enter the node 2 account password in the ensuing log to unlock the node.  A similar 'unlock' confirmation message should appear.


