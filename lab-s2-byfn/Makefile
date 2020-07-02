# Step 1. created folder crypto-config
cryptogen:
	cryptogen generate --config=./crypto-config.yaml 

# Step 2. create channel artifacts
configtx-1:
	configtxgen -profile TwoOrgsOrdererGenesis -channelID syschannel -outputBlock channel-artifacts/genesis.block

configtx-2:
	configtxgen -profile TwoOrgsChannel -outputCreateChannelTx ./channel-artifacts/channel.tx -channelID mychannel 

configtx-3:
	configtxgen -profile TwoOrgsChannel -outputAnchorPeersUpdate ./channel-artifacts/Org1MSPanchors.tx -channelID mychannel -asOrg Org1MSP # i.e. this channel belongs to Org1MSP

configtx-4:
	configtxgen -profile TwoOrgsChannel -outputAnchorPeersUpdate ./channel-artifacts/Org2MSPanchors.tx -channelID mychannel -asOrg Org2MSP # i.e. this channel belongs to Org2MSP


up:
	docker-compose up -d


