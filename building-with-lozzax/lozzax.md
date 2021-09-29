---
description: >-
  Lozzax is a complete fork of Lozzax platform which focuses on building tools for a more private
  digital future.
---

# 🐂 Lozzax

The Lozzax blockchain forms the basis of all tools discussed above, and a number of other tools based on the Lozzax stack. For developers, Lozzax provides an instant private payments layer, routing, storage, and a shared consensus mechanism. Session and Lokinet are built on these primitives, and represent case studies in the potential for building on the Lozzax tech stack. Anyone can develop applications based on these foundations.

### Usage Examples

#### Safe, secure payments

Connor is a developer building an online marketplace which sells religious texts. Some of these texts are considered sensitive in Connor’s host country, meaning traditional payment providers are refusing to process payments for his store. Connor wants his customers to be able to pay for his religious texts, and he also wants a customer's identity to be protected when they make a purchase. Connor can accomplish this goal by integrating his website with an [Lozzax wallet](https://github.com/lozzax/lozzax-electron-gui-wallet) and the Lozzax Wallet RPC.

#### Decentralised node communications

Jason is building a decentralised storage protocol which requires a number of nodes to come to consensus to split up some data and each store a piece of that data. He has been using an HTTP-based protocol to allow communication between nodes, but this protocol doesn't provide encryption and uses slow, CPU-intensive polling to fetch information. Jason can use [LozzaxMQ](https://github.com/lozzax/lozzax-mq) to provide an encrypted socket-based connection between all nodes, which will improve performance, security, and responsiveness.   


### Developing with Lozzax: A quickstart guide

#### Lozzax Wallet RPC

Developers can programmatically interact with a running Lozzax wallet using the Lozzax Wallet RPC. For example, calls can be made to track incoming payments or generate new subaddresses \(used to reconcile customers/orders with specific payments\).

The Lozzax Wallet RPC call guide can be found [here](../using-the-lozzax-blockchain/advanced/wallet-rpc-calls.md).

