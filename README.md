# Develop on Sui Blockchain using Local Docker Enviroment

This is a guideline to explaint step by step how develop Smart Contract using Sui Blockchain on Docker.

## Current Version 

```bash
+ Docker
+ Sui
+ VC 
```
## Prerequisite 

+ Docker Installed

## 1- Install Docker Image from Sui 

This step using Docker Emscripten Image. The name of the container is dcv  ( Docker Computer Vision  ) 
```bash
$ docker run -d --name suidev -p 127.0.0.1:9000:9000 -id  mysten/sui-tools:devnet


```

> [!CAUTION]
> Note: Delete the container use the below command:

 `$docker stop suidev ; docker remove suidev` 

## 2 - Access to Local Sui Blockchain Enviroment

```bash
$ docker exec -it suidev bash
root@cad0e8705e91:/sui#
```

## 3 - Start Local Blockchain 

```bash
root@cad0e8705e91:/sui# nohup sui start  > sui-node.out 2>&1 &
root@cad0e8705e91:/sui# sui client envs
localnet => http://0.0.0.0:9000 (active)
devnet => https://fullnode.devnet.sui.io:443
```

## 4 - Sui Explorer to connect a Local Enviroment 

Open your browser and establish a connection with the local Sui Blockchain environment by accessing Sui Explorer. 
Within Sui Explorer, you'll find four distinct options for connecting to a Sui Blockchain: https://suiexplorer.com/

+ Mainnet
+ Testnet
+ Devnet
+ Local
  
We choose the local configuration on Sui Explorer and connected it to a local Sui Blockchain.

## 5 - Validate a New Account 

Using sui cli command to create a new account on Sui Blockchain 

```bash
root@cad0e8705e91:/sui# 
```

## Reference

[Sui Whitepaper](https://github.com/MystenLabs/sui/blob/main/doc/paper/sui.pdf)

[Sui Docs](https://sui.io/)

[Move Language Docs](https://move-book.com)

[Medium Blog Resource](https://medium.com/coinmonks/web3-environment-using-sui-blockchain-and-docker-a8d31a9b1fe5)

[Docker](https://docker.com)

[Verification](https://link.springer.com/content/pdf/10.1007/978-3-030-53288-8.pdf)

[Keytool] (https://docs.sui.io/references/cli/keytool)

