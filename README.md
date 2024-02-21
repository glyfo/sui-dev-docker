### Develop on Sui Blockchain using Local Docker Enviroment

This is a guideline to explaint step by step how develop Smart Contract using Sui Blockchain on Docker.

#### Current Version 

```bash
+ Docker
+ Sui
+ VC 
```
#### Prerequisite 

+ Docker Installed

#### Install Docker Image from Sui 

This step using Docker Emscripten Image. The name of the container is dcv  ( Docker Computer Vision  ) 
```bash
$ docker run -d --name suidev -p 127.0.0.1:9000:9000 -id  mysten/sui-tools:devnet
```

> [!CAUTION]
> Note: Delete the container use the below command:

 `$docker stop suidev ; docker remove suidev` 

#### Access to Local Sui Blockchain Enviroment

```bash
$ docker exec -it suidev bash
root@cad0e8705e91:/sui#
```

#### Start Local Blockchain 

```bash
root@cad0e8705e91:/sui# nohup sui start  > sui-node.out 2>&1 &
root@cad0e8705e91:/sui# sui client envs
localnet => http://0.0.0.0:9000 (active)
devnet => https://fullnode.devnet.sui.io:443
```

#### Sui Explorer to connect a Local Enviroment 

Open your browser and establish a connection with the local Sui Blockchain environment by accessing Sui Explorer. 
Within Sui Explorer, you'll find four distinct options for connecting to a Sui Blockchain: https://suiexplorer.com/

+ Mainnet
+ Testnet
+ Devnet
+ Local
  
We choose the local configuration on Sui Explorer and connected it to a local Sui Blockchain.

#### Sui Active Address 

Within the environment, there is an active address configured with 5 SUI Object COIN. 
Each of these objects is endowed with 30M, resulting in a cumulative total of 150M in the account. 
The total amount is split in 5 objects.

```bash
root@7a2c0a32cd76:/sui# sui client active-address
0xfc5421865d7a315a513a7fe2faec119af5fce8feb257cf90a78b44d26a533e8d
root@7a2c0a32cd76:/sui# sui client objects 0xfc5421865d7a315a513a7fe2faec119af5fce8feb257cf90a78b44d26a533e8d 2> /dev/null
                 Object ID                  |  Version   |                    Digest                    |   Owner Type    |               Object Type
---------------------------------------------------------------------------------------------------------------------------------------------------------------------
 0x42e64f8fd907c374b9282213b7b79d1cbfb2d6b95a2c2a822cc093e4297e6b30 |     1      | 4MohTVZcRtYM1RLf4Or2sl1TNlWC7r865NE7oQrnvJI= |  AddressOwner   |  Some(Struct(MoveObjectType(GasCoin)))
 0x4cadca66ec64a1d756858d290978884b44367e5d3ddc1589d446f2c156d5b851 |     1      | H49FURXjdIEZBfslS/ablTai4qI0WHqVhbXl7VmH2Vw= |  AddressOwner   |  Some(Struct(MoveObjectType(GasCoin)))
 0x4e40bef4a067bc7b87e62ae7ec82c99c1c0c23f84d2034b8c02c7e326abc2947 |     1      | v9fkqp7h88Dy3StXpCOS0Bsz1g2J0ISOYx0AIkTCu7Q= |  AddressOwner   |  Some(Struct(MoveObjectType(GasCoin)))
 0x6565f4ec3a5f5ac06626370ce582340257ba65c0dea7b614090ce88a35d368cf |     1      | k4aJgf6Q3MYdx4Xqo8bPvrFDW/+s0WyuDtKZN1hTbSE= |  AddressOwner   |  Some(Struct(MoveObjectType(GasCoin)))
 0xdef059bff6c17771b4e5d9485a905f4f1d190848dbb003bbc4906f608673fb8d |     1      | cfWVOLxzLs57eCV9W0JpVntOwBqBthVO7FnH9ny1EjA= |  AddressOwner   |  Some(Struct(MoveObjectType(GasCoin)))
Showing 5 results.
root@7a2c0a32cd76:/sui#
```
#### Create a new Account

```bash
root@cad0e8705e91:/sui# sui keytool generate ed25519 word18
Created new keypair for address wrote to file path "0xcaab851abb53582d95bdcdb46e48e597cca849a1e4b007e478b4368718ccd5b8.key" with scheme ED25519: [0xcaab851abb53582d95bdcdb46e48e597cca849a1e4b007e478b4368718ccd5b8]
Secret Recovery Phrase : [label enforce vague adjust ball lava helmet hunt damage drill option observe spike essay clown baby insane doctor]
root@cad0e8705e91:/sui# sui client objects 0xcaab851abb53582d95bdcdb46e48e597cca849a1e4b007e478b4368718ccd5b8 2>/dev/null
 sui client objects 0xcaab851abb53582d95bdcdb46e48e597cca849a1e4b007e478b4368718ccd5b8 2>/dev/null
                 Object ID                  |  Version   |                    Digest                    |   Owner Type    |               Object Type
---------------------------------------------------------------------------------------------------------------------------------------------------------------------
Showing 0 results.
```

#### Transfer SUI from Active to New Account

This operation transfer a object from Active Account to New Account. 

```bash
root@cad0e8705e91:/sui# sui client transfer --to 0xcaab851abb53582d95bdcdb46e48e597cca849a1e4b007e478b4368718ccd5b8 --object-id  0x42e64f8fd907c374b9282213b7b79d1cbfb2d6b95a2c2a822cc093e4297e6b30 --gas-budget 3000000 2> /dev/null
sui client objects 0xcaab851abb53582d95bdcdb46e48e597cca849a1e4b007e478b4368718ccd5b8 2>/dev/null
                 Object ID                  |  Version   |                    Digest                    |   Owner Type    |               Object Type
---------------------------------------------------------------------------------------------------------------------------------------------------------------------
 0x42e64f8fd907c374b9282213b7b79d1cbfb2d6b95a2c2a822cc093e4297e6b30 |     2      | Xept2720dEuT4x/OnRGo1VdIIzGhGjY6/27M2zl2il8= |  AddressOwner   |  Some(Struct(MoveObjectType(GasCoin)))
Showing 1 results.
```

 More detail : https://medium.com/p/68c07aebb1cb






#### Reference

[Sui Whitepaper](https://github.com/MystenLabs/sui/blob/main/doc/paper/sui.pdf)

[Sui Docs](https://sui.io/)

[Move Language Docs](https://move-book.com)

[Medium Blog Resource](https://medium.com/coinmonks/web3-environment-using-sui-blockchain-and-docker-a8d31a9b1fe5)

[Medium Blog Resource](https://medium.com/coinmonks/sui-explorer-on-local-sui-blockchain-b60fb2c0053e)

[Docker](https://docker.com)

[Verification](https://link.springer.com/content/pdf/10.1007/978-3-030-53288-8.pdf)

[Keytool](https://docs.sui.io/references/cli/keytool)

