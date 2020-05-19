# blockchain-homework

Hi Team! Welcome to the bitnet test network (blockchain).
- To start the network and launch both nodes open two bash (windows) / terminal (mac) instances as each bash window is recognized as a blockchain node by your machine.

- In the first terminal window "cd" into your network where your nodes are and enter: ./geth --datadir node1 --unlock "node1_public_key_here" --mine --rpc --allow-insecure-unlock" to start your first node.

- node1 should start running, when you see "Ethereum Protocol" then "New local node recorded" and "Started P2P networking" that means your first node has successfully started running.

-In the same line as "Started P2P networking" copy the enode key after self= enode://xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx@127.0.0.1:30303

- In the second terminal window, "cd" into your network where your nodes are and enter the following command including the node1's enode to link the two and node2's public key address: ./geth --datadir node2 --mine --port 30304 --bootnodes "enode://xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx@127.0.0.1:30303" --ipcdisable --unlock "node2_public_key_here"

-In the first command, ./geth triggers geth which is an application that launches your blockchain by launching each node. --datadir directs geth to node1, --unlock unlocks the public key address and allows it to mine and this is necessary particularly in a proof-of-authority network. --mine establishes this node as a mining node, --rpc routes to the default rpc port which is http://127.0.0.1:8545 and --allow-insecure-unlock establishes an unsecure connection between the two nodes and since this is a private network, this is fine. 

-In the second command, ./geth triggers geth which is an application that launches your blockchain by launching each node, again --datadir directs to node2, --mine establishes this as a mining node, --port 30304 specifies this node as a 30304 since node1 has taken the place of 30303 as per the end of the self of node1. --bootnodes routes to the bootnode's address via the bootnodes (node1) enode address, --ipcdisable must be entered for windows and --unlock unlocks the second wallets via its public key address  

-The network configurations are as follows: Network name is "bitnet", it is a "proof-of-authority" network, and the chain ID is "7".
node1 pwd: bitnet1
node2 pwd: bitnet2
node1 port: 30303
node2 port: 30304 as 303 is taken by node1
chain id: 7


-In order to connect MyCripto to your accounts, when setting up genesis throguht bash/terminal, add two of your MyCrypto accounts when prompted which accounts are allowed to seal? and Which accounts should be pre-funded? follow the other prompts and export the genesis congiguration. Open MyCrypto, click on change networks, choose create a custom network, call the node and network "bitnet", Currency will be ETH, Chain id is "7" as per the genesis configuration, and the base url is http://127.0.0.1:8545 Once the network is saved, double check that it is selected and connected. 

-To send a transaction, select the keystore file option, go to node1, choose the keytore file and enter the password, once your prompted to node1's wallet, enter node2's public key address in the toAdress slot, choose an amount to send, specify the transaction fee and hit send, this should generate a transaction hash.

-And that's all there is to it, good luck!
