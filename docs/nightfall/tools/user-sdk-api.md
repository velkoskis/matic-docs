---
id: user-sdk-api
title: User API
sidebar_label: User API
description: Application Programming Interface for the User class
keywords:
  - docs
  - polygon
  - nightfall
  - sdk
image: https://matic.network/banners/matic-network-16x9.png
---

The User API serves as an interface that allows for easy interaction with the Nightfall Protocol. The User can be created via the `userFactory` class.

### userFactory.create

Creates an instance of user.
A User can be created with an existing Nightfall mnemonic or without a mnemonic in which case a new mnemonic is generated.

##### Creating an User via Metamask

    const nightfallUser = await UserFactory.create({
      clientApiUrl,
      nightfallMnemonic?
    });

##### Creating an User via a private key

    user = await UserFactory.create({
      blockchainWsUrl,
      clientApiUrl,
      ethereumPrivateKey,
      nightfallMnemonic?
    });

#### user.close

Every instance of an User creates an open WebSocket connection. Using the `close` method destroys the running instance and closes the connection.

    user.close();

### user.makeDeposit

Deposits a Layer 1 token on Nightfall Layer 2

#### Depositing an ERC20 Token

    txReceipts = await user.makeDeposit({
      tokenContractAddress,
      tokenErcStandard,
      value
    });

#### Depositing an ERC721, ERC1155 Token

    txReceipts = await user.makeDeposit({
      tokenContractAddress,
      tokenErcStandard,
      tokenId
    });

### user.checkNightfallBalances

Get the total Nightfall Layer2 balance once the deposit have been processed by the Protocol.(link)

     balances = await user.checkNightfallBalances();

### user.makeTransfer

Transfers tokens on Layer 2 between users.

User [must have balance](https://wiki.polygon.technology/docs/nightfall/tools/user-sdk-getting-started#available-networks) on Layer2 to create a transfer.

#### Transferring an ERC20 Token

    const txReceipts = await user.makeTransfer({
      tokenContractAddress,
      tokenErcStandard,
      value,
      recipientNightfallAddress,
      // isOffChain: true
    });

#### Transferring an ERC721, ERC1155 Token

    const txReceipts = await user.makeTransfer({
      tokenContractAddress,
      tokenErcStandard,
      tokenId,
      recipientNightfallAddress,
      // isOffChain: true
    });

### user.makeWithdrawal

Withdraws a token from Layer 2 back to Layer 1. It can then be withdrawn from the Shield contract's account by the owner in Layer 1.

    const txReceipts = await user.makeWithdrawal({
      tokenContractAddress,
      tokenErcStandard,
      value,
      tokenId,
      recipientEthAddress,
      // isOffChain: true,
    });

### user.finaliseWithdrawal

Allow user to finalise a previously initiated withdrawal and with the given transaction hash

    const txReceipt = await user.finaliseWithdrawal({ withdrawTxHashL2 });

### user.checkStatus

Check client API availability and blockchain websocket connection

    status = await user.checkStatus();

### user.getNightfallMnemonic

Get the Nightfall Mnemonic - Keep this private

    mnemonic = user.getNightfallMnemonic();

### user.getNightfallAddress

Get the Nightfall Layer2 address

    nightfallAddress = nightfallUserRecepient.getNightfallAddress()

### user.updateEthAccountFromMetamask

    updatedAccount = await user.updateEthAccountFromMetamask()

### user.checkPendingDeposits

Check the deposits that haven't been processed yet

    pendingDeposits = await user.checkPendingDeposits()

### user.checkNightfallBalances

Check the balances for Nightfall

     balances = await user.checkNightfallBalances();

### user.checkPendingTransfers

Check the balance of the pending spent commitments on Layer2

    pendingTransfers = await user.checkPendingTransfers()

### user.exportCommitments

Export user [commitments](https://wiki.polygon.technology/docs/nightfall/protocol/commitments)

     export = await user.exportCommitments({
        listOfCompressedZkpPublicKey,
        pathToExport,
        fileName
    });

### user.importAndSaveCommitments

Import user [commitments](https://wiki.polygon.technology/docs/nightfall/protocol/commitments)

    imports = await user.importAndSaveCommitments({
      pathToImport,
      fileName,
      compressedZkpPublicKey,
    });

### Error handling

Today we are handling errors using the NightfallSdkError class, which is a simple implementation of the Error class. We might improve this in the future, but in the meantime make sure to wrap all SDK calls within a try/catch block.
