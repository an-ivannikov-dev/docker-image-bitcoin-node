# Build `ivannikovdev/bitcoin-node` Docker image


## JSON-RPC Interface
> [JSON-RPC Interface](https://github.com/bitcoin/bitcoin/blob/master/doc/JSON-RPC-interface.md).
The JSON-RPC API can be enabled with the -server option.


## Unauthenticated REST Interface
> [Unauthenticated REST Interface](https://github.com/bitcoin/bitcoin/blob/master/doc/REST-interface.md).
The REST API can be enabled with the -rest option.


## Executables
> [bitcoin-core-0.19.1](https://bitcoincore.org/bin/bitcoin-core-0.19.1/bitcoin-0.19.1-x86_64-linux-gnu.tar.gz)

Executables in `/usr/opt/bitcoin/0.19.1/bin/*`:
- bitcoin-cli;
- bitcoind;
- bitcoin-qt;
- bitcoin-tx;
- bitcoin-wallet;
- test_bitcoin.


## Settings file 'bitcoin.conf'
`/root/.bitcoin/bitcoin.conf`
or
`/data/bitcoin.conf`


## Usage
```bash
git clone https://github.com/an-ivannikov-dev/bitcoin-node

cd bitcoin-node/docker
docker build --no-cache --tag ivannikovdev/bitcoin-node .
docker run ivannikovdev/bitcoin-node bitcoind -help
#docker volume create --name=btc_node_data_volume
docker-compose up -d
```

## Building Docker Image

```bash
VERSION=0.19.1

docker build --no-cache --tag ivannikovdev/bitcoin-node:v$VERSION .
docker tag ivannikovdev/bitcoin-node:v$VERSION ivannikovdev/bitcoin-node:latest
docker push ivannikovdev/bitcoin-node:v$VERSION
docker push ivannikovdev/bitcoin-node:latest
```