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

