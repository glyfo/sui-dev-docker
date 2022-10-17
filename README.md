
# Glyfo Command Line Tool for Sui .

glyfclt handler communication with suiX Container to support Web3 Development.

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

## Prerequisite 

+ Docker 
+ wget
+ MacOS ( x86_64 )

## 1- Install 

```bash
$ wget -O /usr/local/bin/glyclt wget -O /usr/local/bin/glyclt https://github.com/glyfo/glyclt-sui/releases/download/v0.3.3/glyclt
$ chmod +x /usr/local/bin/glyclt
$ ./glyclt
 Usage:  glyclt 
+ setup       : manage sui container 
     + status   : validate if suiX is running on enviroment 
     + build    : deploy & install enviroment to develop using sui blockchain 
     + login    : login into container 
     + reset    : restart container ( stop & start ) 
     + info     : show version about software stack 
     + backup   : export suiX container
     + delete   : delete container

v0.3.1

...
```

## 2- Setup 

```bash
$ glyclt setup build # this command building & setup container 
$ glyclt setup stack
----------------------- Release  --------------------
git       | 2.30.2
rustc     | 1.64.0
cargo     | 1.64.0
sui       | 0.10.0
```
## 3 - Generate Public/Secret Key  

```bash
$ glyclt setup login
root@fc8462cf3170:/opt/sui# sui keytool generate ed25519
"ed25519" key generated and saved to '0xd6a2fe5f4d4b11374ee49531bf000fef2c9e6548.key'
root@fc8462cf3170:/opt/sui# exit
exit
...
```

## 4 - Program Config 

```bash
COMMING SOON 
...
```

## Sui Fundamentals

+ Comming Soon 

## Move Smart Contract Examples 

+ Comming Soon

## Reference

[Sui Docs](https://sui.io/)

[Move Language Docs](https://move-book.com)

[Docker](https://docker.com)
