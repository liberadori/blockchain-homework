# blockchain-homework

Hi Team! Welcome to the bitnet test network (blockchain).
- To start the network and launch both nodes open two bash (windows) / terminal (mac) instances as each bash window is recognized as a blockchain node by your machine.
- In the first terminal window "cd" into your network where your nodes are and enter: ./geth --datadir node1 --unlock "node1_public_key_here" --mine --rpc --allow-insecure-unlock" to start your first node.
- node1 should start running, when you see "Ethereum Protocol" then "New local node recorded" and "Started P2P networking" that means your first node has successfully started running.
-In the same line as "Started P2P networking" copy the enode key after self= enode://xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx@127.0.0.1:30303
- In the second terminal window, "cd" into your network where your nodes are and enter the following command including the node1's enode to link the two and node2's public key address: ./geth --datadir node2 --mine --port 30304 --bootnodes "enode://8f0cd4e5736c4105ca32c9e2ee61619d352079e742b718b92ab57b3d05fab3cd8edb26c7d0f80b7996955bd1f84855de7a07c7098305c4c100a6d73ad609af35@127.0.0.1:30303" --ipcdisable --unlock "node2_public_key_here"
