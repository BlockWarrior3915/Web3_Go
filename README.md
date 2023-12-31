<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/kylesliu/web3-go">
    <img src="./assets/img/Ethereum-icon-purple.svg" alt="Logo" width="680" height="256">
  </a>

  <h3 align="center">Web3 Go</h3>

  <p align="center">
    Ethereum Dapp Go API, inspired by 
    <a href="https://github.com/ChainSafe/web3.js">web3.js</a>.
    <br />
    <a href="https://github.com/kylesliu/awesome-golang-algorithm/issues">Report Bug</a>
    ·
    <a href="https://github.com/kylesliu/awesome-golang-algorithm/pulls">Pull Request</a>
  </p>
</p>

[![WEBSITE](https://img.shields.io/badge/Web3-Go-brightgreen)](https://github.com/kylesliu/web3-go)
[![LISTENSE](https://img.shields.io/github/license/6boris/web3-go)](https://github.com/kylesliu/web3-go/blob/main/LICENSE)

## Introduction

This is the Ethereum [Golang API](https://github.com/kylesliu/web3-go) which connects to the Generic [JSON-RPC](https://github.com/ethereum/wiki/wiki/JSON-RPC) spec.

You need to run a local or remote Ethereum node to use this library.

### Client

```bash
go get github.com/6boris/web3-go
```
```go
package main

import (
  "context"
  "fmt"
  "github.com/6boris/web3-go/client"
  "github.com/6boris/web3-go/pkg/otel"
)

func main() { 
  otel.InitProvider()
  ec := client.NewPool(client.GetDefaultConfPool())
  chainID := int64(1)
  v, err := ec.GetClient(chainID).ClientVersion(context.Background())
  if err != nil {
    panic(err)
  }
  fmt.Println(fmt.Sprintf("ChainID:%d ClientVersion:%s", chainID, v))
}


/*
Output:
    ChainID:1 ClientVersion:Geth/v1.11.5-omnibus-65be78cc/linux-amd64/go1.19.7
*/
```

## Development Trips
- [X] Client
  - [ ] Base Method
    - [X] eth_chainId
    - [X] web3_clientVersion
    - [X] eth_gasPrice
    - [X] eth_blockNumber
    - [X] eth_getBalance
    - [ ] ...
  - [ ] Middleware
    - [X] LoadBalance
    - [ ] Monitor
    - [ ] CircuitBreaker
- [ ] Other ...



## Community

- [web3.js](https://github.com/ChainSafe/web3.js) Ethereum JavaScript API.
- [Web3j](https://github.com/web3j/web3j) Web3 Java Ethereum Ðapp API.
- [Web3.py](https://github.com/ethereum/web3.py) A Python library for interacting with Ethereum.

## Provider
- https://public.blockpi.io/


## Dev tool

- [JSON RPC](https://www.jsonrpc.org/specification) Defining the JSON RPC specification.
- [Go Ethereum](https://github.com/ethereum/go-ethereum) Official Golang implementation of the Ethereum protocol.
- [Ethereum 1.0 API](https://github.com/ethereum/eth1.0-apis) Ethereum JSON-RPC Specification.
