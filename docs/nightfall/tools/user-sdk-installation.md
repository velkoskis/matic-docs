---
id: user-sdk-installation
title: Installation
sidebar_label: Installation
description: Nightfall SDK installation process
keywords:
  - docs
  - polygon
  - nightfall
  - sdk
image: https://matic.network/banners/matic-network-16x9.png
---

## Install SDK from NPM

With a client setup
Add the Nightfall SDK as a dependency to your project

```bash
npm install nightfall-sdk
```

To use the SDK, import `UserFactory`.
This will generate an instance of `User` that you should use to perform all the available operations.

```bash
import { UserFactory } from 'nightfall-sdk';

user = await UserFactory.create(userOptions);

const txReceipts = await user.makeDeposit(depositOptions);
```

_Where userOptions is of type UserFactoryCreate and depositOptions UserMakeDeposit_.

Check out the [example scripts](#example-scripts) for a better understanding on how to use the SDK to capacity.
