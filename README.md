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
$ docker run -d --name suidev -p 127.0.0.1:9000:9000 -id  mysten/sui-tools:devnet
$ docker exec -it suidev bash
```

Note: Delete the container image use the below command : 

```bash
$docker stop suidev ; docker remove suidev
```
## 2 - Generate Account A & B 

```bash
$  mkdir A; cd A; sui keytool generate ed25519 word18 ;cd ..
$  mkdir B; cd B; sui keytool generate ed25519 word18 ;cd ..
```

## 4 - Validate the account A & B

```bash
$  mkdir A; cd A; sui keytool generate ed25519 word18 ;cd ..
$  mkdir B; cd B; sui keytool generate ed25519 word18 ;cd ..
...
```


## Reference

[Sui Whitepaper](https://github.com/MystenLabs/sui/blob/main/doc/paper/sui.pdf)

[Sui Docs](https://sui.io/)

[Move Language Docs](https://move-book.com)

[Docker](https://docker.com)

[Verification](https://link.springer.com/content/pdf/10.1007/978-3-030-53288-8.pdf)

[Keytool] (https://docs.sui.io/references/cli/keytool)

