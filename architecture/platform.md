# Platform

## Protocol Layer

MedDAO platform must rely on MedDAO protocol standards, abstractions, primitives and tools to ensure compatibility across all the future applications in the ecosystem.

{% content-ref url="protocol.md" %}
[protocol.md](protocol.md)
{% endcontent-ref %}

## User Identity

### Decentralized Identity

The platform must rely on the decentralized identification (DID) standard for user identity provision and verification across all the layers and features of the system.

## Public Data

### Public Data Storage & Indexing

The platform must provide applications with tools to utilize public data storage access, including indexed collections of data.

It is not strictly specified whether any or all of this data must be decentralized, and the implementation options are still open for discussion.&#x20;

## Private Data

### Private Data Storage & Indexing

The platform must provide applications with tools to utilize private data storage access, including indexed collections of data.

It is not strictly specified whether any or all of this data must be decentralized, and the implementation options are still open for discussion.

### Private Data Encryption & Decryption

The private user data must be encrypted with a mechanism that allows dynamically managed access to decryption keys.

The protocol layer must be used to dynamically check authorization of a particular address before allowing the user to decrypt the data.

## KYC

### KYC Provider Service

The platform should provide or rely on a KYC provider service that translates off-chain human identity into an on-chain proof, such as a specialized NFT.

### Protocol Validation

The proof of KYC should be utilizable across the ecosystem of applications on top of the platform or/and the protocol for the purposes of identity validation and access control.

## Credentials

### Off-chain Credentials Verification Service

The platform must provide or rely on a doctor credentials verification service that translates valid off-chain credentials into an on-chain NFT certificate.

### Protocol Validation

The credentials certificate must be utilizable across the ecosystem of applications on top of the platform or/and the protocol for the purposes of authorization and qualification checks.

## Authorization

### Protocol Authorization Check

The platform must provide tools for applications to utilize the protocol's authorization mechanism in order to:

* Restrict application functionality to certain users;
* Manage encrypted data access;
* Build any other conditional flows;

