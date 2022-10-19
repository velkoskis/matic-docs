---
id: overview
title: Miden VM overview
sidebar_label: Overview
description: "Miden components and structure."
keywords:
  - docs
  - matic
  - polygon
  - miden
  - component
image: https://matic.network/banners/matic-network-16x9.png 
---

Miden VM is a stack machine. The base data type of the MV is a field element in a 64-bit [prime field](https://en.wikipedia.org/wiki/Finite_field) defined by modulus $p = 2^{64} - 2^{32} + 1$. This means that all values that the VM operates with are field elements in this field (i.e., values between $0$ and $2^{64} - 2^{32}$, both inclusive).

Miden VM consists of three high-level components as illustrated below.

![](../assets/intro/vm_components.png)

These components are:
* **Stack** which is a push-down stack where each item is a field element. Most assembly instructions operate with values located on the stack. The stack can grow up to $2^{32}$ items deep, however, only the top 16 items are directly accessible.
* **Memory** which is a linear random-access read-write memory. The memory is word-addressable, meaning, four elements are located at each address, and we can read and write elements to/from memory in batches of four. Memory addresses can be in the range $[0, 2^{32})$.
* **Advice provider** which is a way for the prover to provide nondeterministic inputs to the VM. The advice provider contains a single *advice tape* and an unlimited number of *advice sets*. The latter contain structured data which can be interpreted as a set of Merkle paths.

In the future, additional components (e.g., storage, logs) may be added to the VM.

## Writing programs
Our goal is to make Miden VM an easy compilation target for high-level blockchain-centric languages such as Solidity, Move, Sway, and others. We believe it is important to let people write programs in the languages of their choice. However, compilers to help with this have not been developed yet. Thus, for now, the primary way to write programs for Miden VM is to use [Miden assembly](../user_docs/assembly/main.md).

While writing programs in Assembly is far from ideal, Miden Assembly does make this task a little bit easier by supporting high-level flow control structures and named procedures.

## Inputs and outputs
External inputs can be provided to Miden VM in two ways:

1. Public inputs can be supplied to the VM by initializing the stack with desired values before a program starts executing. Up to 16 stack items can be initialized in this way.
2. Secret (or nondeterministic) inputs can be supplied to the VM via the *advice provider* (described below). There is no limit on how much data the advice provider can hold.

After a program finishes executing, up to 16 elements can remain on the stack. These elements then become the outputs of the program.

Having only 16 elements to describe public inputs and outputs of a program may seem limiting, however, just 4 elements are sufficient to represent a root of a Merkle tree which can be expanded into an arbitrary number of values.

For example, if we wanted to provide a thousand public input values to the VM, we could put these values into a Merkle tree, initialize the stack with the root of this tree, initialize the advice provider with the tree itself, and then retrieve values from the tree during program execution using the `mtree_get` instruction (described [here](../user_docs/assembly/cryptographic_operations.md#hashing-and-merkle-trees)).

In the future, other ways of providing public inputs and reading public outputs (e.g., storage commitments) may be added to the VM.

### Stack depth restrictions
For reasons explained [here](../design/stack/main.md), the VM imposes the following restrictions on stack depth:
1. Stack depth cannot be smaller than $16$. When initializing a program with fewer than $16$ inputs, the VM will pad the stack with zeros to ensure the depth is $16$ at the beginning of execution. If an operation would result in the stack depth dropping below $16$, the VM will insert a zero at the deep end of the stack to make sure the depth stays at $16$.
2. At the end of the program execution, the stack depth cannot be greater than $16$. If ensuring this manually is difficult, [finalize_stack](../user_docs/stdlib/sys.md) procedure can be called at the end of the program execution. This procedure will remove items deep in the stack while keeping the top $16$ items untouched.

### Nondeterministic inputs
The *advice provider* component is responsible for supplying nondeterministic inputs to the VM. These inputs only need to be known by the prover (i.e., they do not need to be shared with the verifier).

The advice provider consists of two components:
* **Advice tape** which is a one-dimensional array of values. The VM can access only the head of the tape. That is, the VM can either remove values from the head of the tape or inject new values at the head of the tape. Formally, this means that the advice tape is actually a stack.
* **Advice sets** which contain structured data reducible to Merkle paths. Some examples of advice sets are: Merkle tree, Sparse Merkle tree, a collection of Merkle paths. Every advice set can be uniquely identified by its root. The VM can request Merkle paths from an advice set, as well as update an advice set by modifying one of its nodes (this will also change the root of the modified advice set).

The prover initializes the advice provider prior to executing a program, and from that point on the advice provider is manipulated solely by executing operations on the VM.
