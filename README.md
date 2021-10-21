## Running the test network

> This modified test-network only supports working with exactly 4 organizations.


How to run:
1. Copy the test-network to your fabric-samples folder, and cd to fabric-samples
```bash
cd test-network
./network.sh up createChannel -s couchdb
cd addOrg3
./addOrg3.sh up -s couchdb
cd ../addOrg4
./addOrg4.sh up -s couchdb
cd ..
```
2. After this use the ordinary chaincode deployment command, it has been automated for 4 organizations.
```bash
./network.sh deployCC -ccn private -ccp /d/Projects/BlockTorrent/master/hlf/blockchain/contracts/secret-sharing/chaincode-go -ccl go -ccep "OR('Org1MSP.peer')" -cccg /d/Projects/BlockTorrent/master/hlf/blockchain/contracts/secret-sharing/chaincode-go/collections_config.json
```