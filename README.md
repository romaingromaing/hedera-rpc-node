# hedera-rpc-node
Minimal needed files to run a hedera mirror node and relay services

**docker-compose.yml** file - with all the services :
- hedera stack (from: https://github.com/hashgraph/hedera-mirror-node.git)
- traefik and nginx (choose your poison, both work)

for the hedera stack (in order to sync) - you need to complete the **application.yml** file with your api keys (be it GCP or AWS).

# hedera relay

**.env.example** file for the relay stack - do a `cp .env.example .env` and set the vars. These are minimal/mandatory.
 
for more, you can check here: https://github.com/hashgraph/hedera-json-rpc-relay/blob/main/docs/configuration.md

obviously, you need to fund the wallet with some HBAR
