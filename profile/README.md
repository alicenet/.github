# AliceNet 1.0

## Introduction

AliceNet is a Layer 2 blockchain designed to facilitate
the **proving** of data ownership and tracking
how data is used (data lineage).
The **cryptographic proofs** ensure data integrity
while shifting the validity to the due-diligence of data author.


## Architecture

AliceNet is built using the
[**Agglayer Chain Development Kit (CDK)**](https://docs.agglayer.dev/cdk/).
Operating as a [**Validium**](https://docs.agglayer.dev/cdk/cdk-erigon/architecture/#cdk-erigon-validium) node,
AliceNet leverages
[**Agglayer zkEVM**](https://github.com/agglayer/agglayer-contracts)
and a
[**Data Availability Committee (DAC)**](https://github.com/0xPolygon/cdk-data-availability)
to deliver a secure, scalable, and low-cost blockchain solution.
We note that the Agglayer zkEVM is a continuation of the Polygon zkEVM.


## Tokens

AliceNet operates on a two-token model: ALCA and ALCB.
ALCA acts as the **governance token**.
ALCB is the **utility token** designed to pay transaction fees inside of AliceNet.
Both tokens follow the ERC-20 standard that exists on the Ethereum blockchain. 

### ALCA

ALCA is the **governance token** of AliceNet;
that is, it is the token used to help guide the AliceNet Layer 2 blockchain.

It is expected that ALCA holders will participate in the governance of AliceNet.
This will involve voting,
and the total votes will be determined by the amount of ALCA;
thus, holding more ALCA leads to greater influence on the direction of AliceNet.
Additionally, a portion of the proceeds garnered from minting ALCB
will be distributed between ALCA holders;
this specifics of this distribution will be discussed later.

### ALCB

ALCB is the **utility token** of AliceNet;
that is, it is the token used to pay for all blockchain operations.
In particular, ALCB will be used to compensate the Sequencer and Aggregator
of AliceNet.

It can be purchased (minted) on Ethereum for ETH and then transferred
to AliceNet to be used;
once transferred, Layer 2 ALCB **cannot** be moved back to Ethereum.
Additionally, once minted ALCB **cannot** be burned
in order to receive ETH.
Both of these rules are in place because ALCB has one purpose: 
to pay for AliceNet operations.
In the future, a portion of the proceeds from minting ALCB will be distributed
to [ALCA](./alca_discussion.md) holders
(as one of the benefits of holding the ALCA Governance Token).

All projects built on AliceNet will use ALCB to pay for operations.


## Identity and Credentials

Some projects on AliceNet use Decentralized Identifiers (DIDs),
Verifiable Credentials (VCs), and Verifiable Presentations (VPs).
These are based on the [W3C DID Specification](https://www.w3.org/TR/did-core/)
and [W3C VC Specification](https://w3c.github.io/vc-data-model/).
In this case, AliceNet will store DID documents needed to verify proofs;
thus, AliceNet provides its own Public Key Infrastructure (PKI).


## Proofs and Verification

The cryptographic proofs used within VCs and VPs are based on BBS signatures
(a type of digital signature which uses a bilinear pairing)
and Merkle trees.
A discussion of BBS signatures and associated zero-knowledge proofs
may be found in a [recent paper](https://eprint.iacr.org/2023/275).


## Conclusion

Data is critically important, and AliceNet is the Layer 2 blockchain
which provides the necessary infrastructure to prove the lineage and value of data.