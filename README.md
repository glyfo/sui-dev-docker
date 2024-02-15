# GLYFO Command Line Tool for Sui.

gclt to support Sui Development.
[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

## Current Version 

```bash
+ Docker
+ Sui 
```
## Prerequisite 

+ Docker Installed

## 1- Install Docker Image from Sui 

This step using Docker Emscripten Image. The name of the container is dcv  ( Docker Computer Vision  ) 
```bash
$ docker run -d --name suib -p 127.0.0.1:9000:9000 -id  mysten/sui-tools:devnet
$ docker exec -it suib /bin/bash
root@78362416c8aa:/sui# apt-get -qq update
root@78362416c8aa:/sui# apt-get -qq upgrade
root@78362416c8aa:/sui# apt-get -y install wget
root@78362416c8aa:/sui# wget -O /usr/local/bin/gclt https://github.com/glyfo/glyclt-sui/releases/download/v0.3.5/gclt

```
## 2- Check Current Stack

```bash
$ gclt stack
----------------------- Release  --------------------
git       | 2.30.2
rustc     | 1.64.0
cargo     | 1.64.0
sui       | 0.10.0
```
## 3 - Generate Account A 

```bash
$ gclt wallet A
...
```

Note : This command use a sui keytool generate ed25519 command. 

## 4 - Generate  Account B 

```bash
$ gclt wallet A
...

## 4 - Transfer SUI from A to B Account 

```bash
$ gclt transfer A B
...


## Reference

[Sui Whitepaper](https://github.com/MystenLabs/sui/blob/main/doc/paper/sui.pdf)

[Sui Docs](https://sui.io/)

[Move Language Docs](https://move-book.com)

[Docker](https://docker.com)

[Verification](https://link.springer.com/content/pdf/10.1007/978-3-030-53288-8.pdf)


