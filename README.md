# hedera-rpc-node
Minimal needed files to run a hedera mirror node and relay services

**docker-compose.yml** file - with all the services :
- hedera stack (from: https://github.com/hashgraph/hedera-mirror-node.git)
- traefik and nginx (choose your poison, both work)

for the hedera stack (in order to sync) - you need to complete the **application.yml** file with your api keys (be it GCP or AWS).

**.env.example** file for the relay stack - do a `cp .env.example .env` and set the vars : 

# Mainnet
CHAIN_ID=0x127
HEDERA_NETWORK=MAINNET
#MIRROR_NODE_URL=http://traefik:8089
#MIRROR_NODE_URL=http://api-proxy:8080
#uncomment one of the above
#mandatory env variables to support queries and transactions to Consensus Node e.g. eth_sendRaTransaction and fallback scenarios on calls to Mirror Node
OPERATOR_ID_MAIN=
#<AccountID e.g. 0.1.2, can be obtained from portal.hedera.com, wallet or exchange of choice>
OPERATOR_KEY_MAIN=
#<DER or ECDSA Encoded Private Key, can be obtained from portal.hedera.com, wallet or exchange of choice>
OPERATOR_KEY_FORMAT: HEX_ECDSA
# Required to use EVM based private key
RATE_LIMIT_DISABLED=true

obviously, you need to fund the wallet with some HBAR
