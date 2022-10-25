---
id: graph-data
title: Using subgraphs
sidebar_label: Using Polygon's root subgraph
description: Learn how to use Polygon's subgraph for data
keywords:
  - docs
  - matic
  - polygon
  - the graph
  - data
  - analytics
  - index
  - indexing
  - query
image: https://matic.network/banners/matic-network-16x9.png
---

# Polygon Root Subgraph Introduction

Polygon has a GraphQL API Endpoint hosted by [The Graph](https://thegraph.com/docs/about/introduction#what-the-graph-is) called a subgraph for indexing and organizing data from the Polygon smart contracts.

This subgraph can be used to query on-chain Polygon data. The subgraph data is serviced by a decentralized group of server operators called [Indexers](https://thegraph.com/docs/en/network/indexing/).

The PolygonRoot subgraph works by listening for events emitted by one or more data sources (Smart Contracts) on the various chains. It handles the indexing and caching of data which can later be queried using the GraphQL API Endpoint, providing an excellent developer experience.


## Helpful Resources

- [Video Tutorial on creating an API Key](https://www.youtube.com/watch?v=UrfIpm-Vlgs)
- [Managing your API Key & setting your indexer preferences](https://thegraph.com/docs/en/studio/managing-api-keys/)
- [Querying from an application](https://thegraph.com/docs/en/developer/querying-from-your-app/)
- [How to use the explorer and playground to query on-chain data](https://medium.com/@chidubem_/how-to-query-on-chain-data-with-the-graph-f8507488215)
- [Explorer Page](https://thegraph.com/explorer/subgraph?id=FDrqtqbp8LhG1hSnwtWB2hE6C97FWA54irrozjb2TtMH&view=Overview)
- Graphql Endpoint: https://gateway.thegraph.com/api/[api-key]/subgraphs/id/FDrqtqbp8LhG1hSnwtWB2hE6C97FWA54irrozjb2TtMH
- [Code Repo](https://github.com/maticnetwork/subgraphs)
