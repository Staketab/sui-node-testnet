# SUI NODE SETUP
Setup Sui Testnet node.

## 1. Install Docker-compose:
```
wget -q -O - https://bit.ly/3OcdIfO | bash -s -- 1.29.2
```
## 2. Clone repository:

```
cd && git clone https://github.com/Staketab/sui-node-testnet.git
cd sui-node-testnet
```

## 3. Download Genesis:
```
wget -O $HOME/sui-node-testnet/genesis.blob https://github.com/SuiExternal/sui-external/raw/main/genesis.blob
```
## 4. Start the Node
Run this command to start the node:  
```
docker-compose up -d
```
-------------------------------
# REDEPLOY SUI NODE
After releasing new releases in Sui, you need to redeploy the node with the commands below:
```
cd sui-node-testnet
docker-compose pull
docker-compose down --volumes
rm -r $HOME/sui-node-testnet/suidb $HOME/sui-node-testnet/genesis.blob
wget -O $HOME/sui-node-testnet/genesis.blob https://github.com/SuiExternal/sui-external/raw/main/genesis.blob
docker-compose up -d
docker-compose logs -f sui
```

Other commands:
1. Stop docker-compose
```
docker-compose down
```
2. Docker-compose logs
```
docker-compose logs -f sui
```

# DONE