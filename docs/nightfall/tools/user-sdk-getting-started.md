---
id: user-sdk-getting-started
title: Getting Started
sidebar_label: Getting Started
description: Getting Started
keywords:
  - docs
  - polygon
  - nightfall
  - sdk
image: https://matic.network/banners/matic-network-16x9.png
---

## What is a Nightfall Client?

The Nightfall Client is a key part of the architecture. It generates zero-knowledge proofs, stores zero-knowledge commitments and interacts with the contracts. The SDK uses Nightfall Client to interact with the Nightfall Protocol.

**To be able to use the SDK one must have a running instance of the Client**.

### Setup a Client locally (Ganache)

To use the SDK locally, set up and run the entire Nightfall project. The Client is part of this setup and by running the Project you are running the Client too.

You will also need a running proposer, therefore you should use two terminals, one for running Nightfall and one for the Proposer.

**Setup and run Polygon Nightfall**

```bash
git clone https://github.com/EYBlockchain/nightfall_3.git
cd nightfall_3
./setup-nightfall
./start-nightfall -g -d
```

**Run the Proposer**

```bash
# terminal 2, also cd into nightfall_3
./start-apps
```

### Setup a Client in testnet (Goerli)

To use the SDK on a testnet you should only have a Client running, other parts of the infrastructure like the Proposer are provided.

```bash
git clone https://github.com/EYBlockchain/nightfall_3.git
cd nightfall_3
./setup_nightfall
cd nightfall_3/nightfall-client
```

**Setup Client**

Rename `client-example.env` to `.client.env` and update the contents as following:

```
ETH_NETWORK=goerli
BLOCKCHAIN_URL=your web3 url provider to access the blockchain
```

**Run Client**

```bash
./start-client
```

## Available networks

Polygon Nightfall has been thoroughly tested on `ganache` and `goerli`. On Goerli we provide most of the infrastructure required to run Nightfall, except for the client.

#### 2Tx rule

**Applies to Nightfall Protocol on Ganache**

Making a deposit, transfer or withdrawal means that a transaction is submitted to L2, when 2 transactions like this are submitted a block is proposed and created. The creation of a new block changes the state of Nightfall. Changing the state of L2 means that the deposit, transfer and withdrawal (not finalise-withdrawal) are finalised.

E.g. Making 1 deposit won't change the state of Nightfall. Running the `eg:ganache:balances` script won't show any updated balance with the new deposit. Making 2 deposits or a deposit and a transfer will update the state and show the correct updated balance when running the script.

#### 32Tx rule

**Applies to Nightfall Protocol on Goerli Testnet**

The 32Tx rule is essentially the same as the `2Tx rule` but with 32 transactions instead of 2.

To learn more about Nightfall protocol visit the [documentation](https://docs.polygon.technology/docs/nightfall/faq/#how-long-do-transfers-take-on-polygon-nightfall-network-from-start-to-finish).
