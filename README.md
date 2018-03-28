# Hyperledger-Apps

Hyperledge sample applications and models. PLease drill down into individual projects for more info.

---

## Fabric Setup

1. Please refer to prerequisite setup documentation here: https://hyperledger.github.io/composer/latest/installing/installing-prereqs.html#ubuntu

2. Development environment setup: https://hyperledger.github.io/composer/installing/development-tools.html

### Common commands after installation

```shell
# Download docker images
$ ./downloadFabric.sh

# Start fabric - Spins up docker containers including peers, orderer, CA etc.
$ ./startFabric.sh

# Create teh Peer Admin card to connect to the fabric environment
$ ./createPeerAdminCard.sh

# Stop fabric
$ ./stopFabric.sh
```
