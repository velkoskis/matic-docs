---
id: faq
title: FAQ
description: Build your next blockchain app on Polygon.
keywords:
  - docs
  - matic
image: https://matic.network/banners/matic-network-16x9.png
---
## What is Polygon?

Polygon is a sidechain based scaling solution for public blockchains. Polygon provides scalability while
ensuring a superior user experience in a secured and decentralized manner. It has a working implementation
for Ethereum on Kovan Testnet. Polygon intends to support other blockchains in the future which will enable
it to provide interoperability features alongside offering scalability to existing public blockchains.

## How is Polygon different from other implementations of Plasma?

Polygon's implementation of Plasma is built on state-based side chains which run on EVM, while the other implementations of Plasma primarily use UTXOs which restricts them to being payment specific. Having state based side chains allows Polygon to provide scalability for generic smart contracts as well.

Secondly, Polygon uses a public checkpointing layer which publishes checkpoints after periodic intervals (unlike checkpoints  after every block in Plasma Cash) allowing the side chains to operate at high speeds while publishing the checkpoints in batches. These checkpoints along with the fraud proofs ensure that Polygon's side chains operate in a secure manner.

## Your project provides scalability for Ethereum using plasma chains, is it a protocol or a native blockchain in itself?

Polygon Network is a "side chain" solution where Ethereum mainchain assets, i.e. all Dapps/Tokens/Protocols of the main chain can be moved/migrated to Polygon side chain(s) and when needed, one can withdraw assets back to mainchain.

## What are the competitive advantages of Polygon over its competitor?

- L2 scaling solutions

Polygon is committed to achieving scale with decentralization. Polygon uses periodic checkpoints and fraud proofs. When users want to withdraw their assets, they use the checkpoints to prove their assets on side-chain, while fraud proofs are needed to challenge fraud or any bad behavior and slash stakers.

Other projects like Loom are also offering L2 scaing solutions. Loom recently announced plans of Zombiechain that may have similarities to Polygon. But there two key elements that we differ on:

First and foremost,The focus is different. Loom is focusing on games and social apps (requiring relatively less decentralization) while Polygon is focusing on not just financial transactions/ trades but games and other casual Dapps as well. We also have plans for full-blown financial services like lending/trading DApps (token swaps, margin trades and much more)

Secondly, Plasma Cash, which is what we believe Loom wants to use "in future", will have block times greater than the Ethereum block times as you need to push every block of the sidechain to the main chain, while Polygon uses checkpoints for 1-second block times (with PoS layer)

As Plasma Cash works with Non-Fungible Tokes (NFT), it works great for game cards and social state changes where you have pre-defined fees (bundled as NFT - eg "20 tokens" to play game equals 1 NFT coin on plasma cash). For normal token transfers, you may need to swap tokens (like currency notes & change) on top of plasma cash which makes it difficult to implement while offering a friendly UX. It is still being discussed on plasma calls, while Polygon uses state-based plasma (closer to Plasma MVP).

- L1 scaling solutions

Apart from that, amongst other scaling projects like Ziliqa and Quarkchain, Polygon stands out due to its ability to achieve scale while maintaining a great degree of decentralization.

More importantly, these scalability projects have a reinventing the wheel problem. They are creating new blockchains where the developer community, product ecosystem, technical documentation and more importantly businesses need to be built from "scratch". Polygon on the other hand, it being an EVM enabled chain,  programming language, developer documentation etc is available off the shelf to Polygon. All the Dapps/assets built on Ethereum mainchain have scalability available at the click of a button. This is made possible by Polygon being an EVM based side chain.

- Payments

In payments, Raiden Network can be a competitor. Raiden thas implemented Lightning network on Ethereum. An important issue is of capacity/liquidity on the hubs. But this issue gets further amplified for Raiden as Lightning network has only one asset (Bitcoin) for hubs to maintain liquidity while Raiden Network would have to achieve liquidity for the countless number of assets (Ether, ERC20 Tokens)

We believe that Polygon has an edge in terms of usability because, in Raiden, both sender and receiver have to create their payment channels. This is very cumbersome for users. While with Polygon's underlying technology there is no requirement of payment channels for users and they only need to have a valid Ethereum address to receive tokens. This is also in line with our long-term vision of improving the user experience for decentralized applications.

- Trading and Finance

Polygon intends to enable DEX's (eg 0x), Liquidity pools (eg. Kyber Network) and other kinds of financial protocols like Lending protocols (Dharma Protocol) on its platform, which will allow Polygon users acees to varied financial serivce applications like DEXs, Lending DApps and many others

- Others

Also, Polygon's core focus on creating applications having an enhanced user experience will aid in the mass adoption of DApps. For the same end objective, we are intent on building ecosystem tools. Our products like Dagger (which is well known in the Ethereum community) and Opensigner (implementation of Walletconnect protocol and complete Node.js implementation) are a testimony to the same -

[WalletConnect](https://github.com/WalletConnect/walletconnect-monorepo)

[Dagger](https://github.com/maticnetwork/eth-dagger.js)

[Sol-Trace](https://github.com/maticnetwork/sol-trace.js)


## How does Polygon compare with other sidechain solutions like POA/Go-Chain?

Projects like POA use block producers notarised by Government and Go-Chain relies on institutions across various countries. Such public block producers have a big chance of getting influenced by powerful external agencies and self-interests. Also, side chain transactions are secured only by side chain consensus in which the participants are very low in number 3-25 while on Polygon, all side transactions are secured by multiple mechanisms on the side chain as well as mainchain.

On sidechain, any transactions done by Block producer layer are verified and checkpointed to the mainchain by a highly decentralized checkpointing layer. So if any fraudulent transaction happens on sidechain it can be detected and handled by the checkpointing layer. Even in extreme and highly unlikely scenario wherein the block producer layer as well as the checkpointing layer both collude, even then Mainchain has fraud proofs on which anyone from the public can come and challenge any transaction that they deem fraudulent on the sidechain. If the challenge is successful, there is a huge economic disincentive/financial punishment to the colluding parties as their stakes are slashed. Also, the public challenger is rewarded with slashed stakes of the fraudulent sidechain actors.

This makes Polygon an economically incentivized side chain network which has a high degree of decentralization and security of the sidechain transactions.

Secondly, capacity and TPS of Polygon sidechains are much higher than that of POA and Go-chain. Especially when Polygon can have thousands of transactions while POA and Go-chain are single sidechains which have a higher limit of a few thousand transactions.

## Via what principles will new Side Chains be added? Will there be any special requirements for private companies' local Side Chains?

Relative to state channels, Plasma represents a superior alternative to scaling frameworks, chiefly due to the security guarantees provided by the framework - which basically say that users will never lose funds in any eventuality. Sure, there could be delays in getting back the money, but a Byzantine Plasma operator cannot create money out of thin air, or double spend a transaction.

Polygon will strive to be a completely open and public blockchain infra in the future wherein the economic incentives/disincentives will primarily drive the security and stability of the system. So anyone should be able to join the system and participate in the consensus. In the network seeding stage however, initially Polygon will have to play a larger role to enable side chains.

Also, Polygon side chains would be primarily public side chains i.e sidechains available for use for anyone in public just like other public blockchains. Although, Enterprise Polygon chains will intend to provide dedicated side chains (non-privacy enabled) for particular organizations. The security and decentralization of such chains would still be kept intact using the checkpointing layer and fraud proofs on the mainchain. However, supporting privacy enabled sidechains with checkpoint validation and fraud proofs on the mainchain is still a research topic for us. We are looking into new technologies like zkSNARK and zkSTARK.

## How is Polygon different than Celer Network?

Both Polygon  and Celer Network are different solutions to the same problem - low transaction throughput in current blockchains. Both utilise off-chain scaling techniques and rely on the main chain for final security; however the fundamental difference is in the approaches - Polygon is based on a set of Plasma sidechain(s) backed by Proof-of-Stake consensus (see https://plasma.io/ for more details), whereas Celer Network is a state-channel based solution. Both projects aim for generalized state transitions off-chain, but in vastly different ways.

Polygon is aiming to build a DApp developer ecosystem. Since it uses an account-based Plasma sidechain, and also employs a EVM-compatible runtime known as the Polygon VM, it will be relatively easier for Ethereum based DApps to migrate to Polygon once it is live. So in this respect as well, Celer Network is different in terms of developer interfacing.

## Will side chains also be synced with the Mainchain (Ethereum)?

Absolutely. The public checkpointing layer will validate all the transactions happening on the side chains and publish the proofs to the mainchain. To ensure foolproof security of side chain transactions, the mainchain Plasma contract contains various kinds of Fraud Proofs where any sidechain transactions can be challenged for any fraudulent activity. If a challenger succeeds, the stakes of the side chain actors involved in the fraud are slashed and are transferred to the challenger. This is equivalent to an ever running high stake bug bounty.A good diagram for understanding is as below:.

![Screenshot](../../static/img/matic/Architecture.png)

## Will you implement atomic swaps? If yes, how?

There are ways to do so - Swingyby protocol, Doge/ETH bridges [check this Medium article](https://medium.com/truebit/enter-the-rabbit-hole-the-doge-ethereum-art-project-31e8116043c4), hash time locked contracts or simple pegging. We will choose best suited with UI/UX and security as we go ahead. Once assets from multiple blockchains are available on the sidechain, DEXs will be able to provide exchange between assets which are originally from different base chains.

## At the end of the White Paper, there is a list of "Potential Use Cases" - will all of that be implemented? In what order?

Polygon Foundation will enable and support ecosystem teams to develop these potential use cases. It is not our intention to implement all of these projects on our own - and we do not wish to give off that impression. We intend Polygon to be a DApp platform, which will provide instant transactions at low costs. Once the Polygon goes live, we will keep adding support to all these use cases. We will be leaning on community teams to work with us on our platform to create these apps.

The basic logic is - if there is a DApp/Protocol which is working on Ethereum, but is limited by low transaction throughput and high transaction fees - then we will be able to add support for these DApps/Protocols on Polygon.

The ultimate objective is to come up with Generalized State Scaling - however, this will take time. We are already working with teams such as Parsec Labs, Truebit and Decentraland on this initiative - A are few mentions about Matic from other projects, [here](https://parseclabs.org/blog/Development-Update-May-2018/) and [here](https://blog.decentraland.org/blockchain-security-will-it-scale-5d82c5df4640).

But before that happens, we will add support for specific contracts and protocols. Once the contract is secured by Fraud proof guarantees, it can go live on Polygon, and can be used by DApps.

Priority order would be DEX, Payments, Liquidity Providers, Lending & Credit Scoring, Atomic Swaps.

Although most of these features will run in parallel, we are in talks with various top teams to collaborate with us to deploy these protocols on Polygon side chains.

## Why will it be difficult to replicate Polygon's plasma implementation?

Although with blockchain solutions its more about the network effect as to which network is able to scale/grow ecosystem better than others BUT more importantly with blockchain solutions they have to mandatorily be open source as it entails the actual assets being used in them.

Also it is the case with all the open source projects. It is equally applicable to us as well as the other rival implementations as we are going to have our GPL licence which mandates anyone using our implementation to mandatorily open source their code. But again, the point being, that copying of code is applicable to even to Bitcoin, Ethereum and any other projects, its more about the network effect that one project can achieve.

## What’s special about Polygon Network’s Plasma implementation?

So Plasma Polygon uses a account based model system rather than the UTXO system used by Plasma Cash, Plasma MVP and Plasma XT. This provides us with a huge advantage of using an EVM on the Polygon chain which enables us to utilize the entire Ethereum ecosystem, developer tools, integration libraries etc for the Polygon.

The Dapps can easily use the the Polygon system without making any changes to their ERC20 tokens. Also our checkpointing layer enables us to be magnitudes of times faster than the other Plasma implementations as we batch the proofs of the individual blocks in the checkpoints while other Plasma implementations have to submit every block proof to the mainchain

## How are you going to solve the issues with centralization?

Here is a diagram to give you some context:

![Screenshot](../../static/img/matic/Merkle.png)

So firstly, The PoA nodes that you saw, are going to be Delegates ( with Proof of Solvency i.e They have to deposit high amount of stake ) and KYC basically selected by the PoS layer just like a EOS style DPoS or DBFT nodes.

Secondly, let’s assume all of the Delegates (or 2/3rd of them) turn bad actors and produce faulty blocks, then you have PoS layer stakers who are going to validate all the blocks and if any frauds are committed the stakes of Delegates are slashed, the checkpointing is stopped for the corrective actions.

Thirdly, let's say even the Staker PoS layer (which would be a large number of nodes) also turns bad and collude to produce faulty checkpoints. I.e all the PoA are corrupt and PoS are corrupt Even then following Plasma philosophy we are writing one of the coveted things of side chain scaling, **Fraud proofs** which is being watched by many big projects ( The watchers can be seen as our repository watchers on GitHub). This fraud proof mechanism enables any one in public to challenge any transaction on the Mainchain.

## Why is Matic Token required?

The following reasons reinforce the need of having Matic token

### Polygon intends to be a general purpose scaling solution for public blockchains:
We are starting out on Ethereum as our first base chain, but in the future Polygon can be deployed on multiple base chains. There will be other basechains added soon, So it won’t make sense to have one currency (ether) to be used for paying fees on the sidechains. If there's an existential concern over any basechains future, having that basechains’ currency as native asset for the Polygon will cripple the scaling network. Therefore it is important to build the Staker ecosystem on Polygon's own network token.

### Appcoin security model:
Polygon intends to enable Dapps to pay Polygon fees in Dapp-coins by abstracting a token swap mechanism using a liquidity pool like Kyber. The user simply uses her Dapp-coins to pay fees, in the background the Dappcoin is swapped for Matic tokens. Hence the DApp developers who want to provide a seamless user experience will help maintain a Polygon liquidity pool.

### Seeding the network in nascent stages:
It’s practically impossible to seed the system when there are little to no txns in the network at the start, as we cannot distribute Eth to the highly decentralized Validator layer and the block producers. Whilst with Matic tokens, we have provisioned a large percentage of tokens to be distributed for seeding block producer, checkpointer stakes and subsequently offer block rewards. This provision ensures that the stakers receive rewards even if the network takes some time to assume network effects. It is akin to why Block Mining rewards were kept for Bitcoin, stakers and block producers can be incentivized in this way to keep the network secure.

If your concern is about Devs, one of the pillars of our strategy is to keep the entry barrier for devs very low. We have made sure that all the Ethereum dev tools work out of the box on Polygon. In terms of the tokens needed for paying fees on testnet, it is no different for a developer developing on Ethereum. The dev gets free tokens for the testnet from a Polygon faucet and gets going, just like it is on Ethereum. You need Matic tokens only when you want to deploy on Polygon Mainnet, where the gas fee is much lower than Ethereum, around 1/100th of a txn fee you pay on Ethereum.

## What drives the use and demand for Matic tokens?

There are two primary uses of the token:

1. The token is used to pay for the transaction fees in the network
2. The token is used for staking to participate in the Proof of Stake consensus mechanism for checkpointing layer and block production layer

**Some of the secondary reasons for token demand**:

* Polygon Network intends to enable Dapps to pay Polygon fees in Dapp-coins by abstracting a token swap mechanism using a liquidity pool like Kyber. The user simply uses her Dapp-coins to pay fees, in the background the Dappcoin is swapped for Matic tokens. Hence the DApp developers who want to provide a seamless user experience will help maintain a Polygon liquidity pool.

* To enable faster exits we are implementing a lending mechanism using Dharma Protocol wherein an underwriter/lender can receive the exit-token and disburse the exit amount with a small fee as interest. The lender then claims the tokens after one week by using exit-token. The user thus gets near immediate withdrawals while the lenders can earn interest for the service they provide.

**Protocol Level burning of tokens**

We intend to burn a percentage of transaction fee in every block. This makes the tokens deflationary in nature and provide it a constant support in terms of its value at the protocol level.

**Low entry barrier (and hence higher chances of quick adoption)**

We will heavily lean on DApps to bring in end-user adoption. One of the key features is that we maintain an architecture which is fully compatible to Ethereum development ecosystem i.e all smart contracts, wallets, IDEs, DevOps tools etc are directly compatible with Polygon. Any Ethereum Dapp can be ported to Polygon without almost no significant changes. So the entry barriers for existing Ethereum developers to transition to  Polygon are negligible which can jumpstart a viral Dapp adoption.This has the potential to bring in a lot of organic demand due to Network effects that build around the Polygon.


## Do you have prototype or demo to show to the public yet?

Yes. The demo is available [Here](https://www.youtube.com/watch?v=l1vb5pjezJ8)

## What is the transaction per seconds?

Currently “a single Polygon side chain” can theoretically handle 7,000+ transactions per second.

## Is token type ERC20?

Yes. And the same token will be applicable to MatPolygonic Chain too i.e no need to move to a native token in future

## Do you have a timeline on the Alpha Mainnet launch?

Most likely Q3 or early Q4.

## Could you outline your roadmap, How far are you with development and When do you expect a live implementation of Matic to be launched?

We already have a implementation live. We have recently put it on youtube. We also conducted Consensys BSIC in Mumbai where we demoed Polygon on Kovan Testnet.
In terms of the Roadmap, we are going to publish a detailed roadmap soon.

## What is the expected TPS you'll be able to bring to the Ethereum network? What are you running at now on testnet?

A single side chain has the capacity of 7,000+ transactions per second. Polygon has the capability to add multiple side chains, But currently, our focus would be on stabilizing the network with one side chain.

## "We have chosen Ethereum as the first platform to showcase our scalability" What other platforms are you aiming toward, and is there a timeline for implementation

Making our Mainnet live on Ethereum is the first priority as of now. Once we have a stable implementation of our Testnet ready we will announce our plans for other Blockchains.

## "We also intend to launch the alpha version of our Mainnet with working Dapps before the Token sale"

The partner information is confidential as of now. We will soon make them public. We have 4 teams building their solutions on top of Polygon. One of them is a banking wallet in India, 1 in gaming segment, 1 in referral marketing (who are going to publish about Polygon in the Whitepaper) and 1 in the ad network. There are others in pipeline but are not yet finalized.

## Do you have a timeline on the Token sale? Any information on these DApps?

Token sale related details are again confidential as of now.
