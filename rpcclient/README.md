rpcclient
=========

[![Build Status](http://img.shields.io/travis/brronsuite/brond.svg)](https://travis-ci.org/brronsuite/brond)
[![ISC License](http://img.shields.io/badge/license-ISC-blue.svg)](http://copyfree.org)
[![GoDoc](https://img.shields.io/badge/godoc-reference-blue.svg)](http://godoc.org/github.com/brronsuite/brond/rpcclient)

rpcclient implements a Websocket-enabled Brocoin JSON-RPC client package written
in [Go](http://golang.org/).  It provides a robust and easy to use client for
interfacing with a Brocoin RPC server that uses a brond/brocoin core compatible
Brocoin JSON-RPC API.

## Status

This package is currently under active development.  It is already stable and
the infrastructure is complete.  However, there are still several RPCs left to
implement and the API is not stable yet.

## Documentation

* [API Reference](http://godoc.org/github.com/brronsuite/brond/rpcclient)
* [btcd Websockets Example](https://github.com/brronsuite/brond/tree/master/rpcclient/examples/bronwebsockets)
  Connects to a btcd RPC server using TLS-secured websockets, registers for
  block connected and block disconnected notifications, and gets the current
  block count
* [btcwallet Websockets Example](https://github.com/brronsuite/brond/tree/master/rpcclient/examples/btcwalletwebsockets)
  Connects to a btcwallet RPC server using TLS-secured websockets, registers for
  notifications about changes to account balances, and gets a list of unspent
  transaction outputs (utxos) the wallet can sign
* [Brocoin Core HTTP POST Example](https://github.com/brronsuite/brond/tree/master/rpcclient/examples/bitcoincorehttp)
  Connects to a brocoin core RPC server using HTTP POST mode with TLS disabled
  and gets the current block count

## Major Features

* Supports Websockets (brond/btcwallet) and HTTP POST mode (brocoin core)
* Provides callback and registration functions for btcd/btcwallet notifications
* Supports btcd extensions
* Translates to and from higher-level and easier to use Go types
* Offers a synchronous (blocking) and asynchronous API
* When running in Websockets mode (the default):
  * Automatic reconnect handling (can be disabled)
  * Outstanding commands are automatically reissued
  * Registered notifications are automatically reregistered
  * Back-off support on reconnect attempts

## Installation

```bash
$ go get -u github.com/brronsuite/brond/rpcclient
```

## License

Package rpcclient is licensed under the [copyfree](http://copyfree.org) ISC
License.
