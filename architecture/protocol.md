# Protocol

## Tokenized Identity

### Proof of KYC

The protocol must define or support a non-transferable token encoding a proof of KYC.

Holding this token would be optional for any address, however it will allow for some features to be gated using it.

## MedCred Certification

{% hint style="info" %}
Information regarding the MedCred Certification can be found using the link below:&#x20;
{% endhint %}

{% content-ref url="../tokenomics/medcred.md" %}
[medcred.md](../tokenomics/medcred.md)
{% endcontent-ref %}

## Authorization

### Roles and Permissions

It is proposed to manage the access to the various features of the protocol by using a role-based authorization model, in which any address can be assigned one or more of the pre-defined roles or permissions.

For example:

* Guest
* Member
* Guard
* Certification Authority
* Treasury Manager
* Governor

### Authorization Checks

This authorization feature would serve two primary purposes:

1. Act as an on-chain authorization provider for any smart-contract or decentralized application to rely on when implementing gated access to any data or action.
2. Prevent unauthorized on-chain state mutation by guarding the protocol implementation functions with with the corresponding role or permission checks.

### Upgrading & Downgrading Authorization

Any address in the protocol can have its roles or permissions changed by making an authorized transaction. It is likely that such an action should also be approved by a governance decision / voting.&#x20;

## Protocol Abstractions

### Baseplate / Hyperstructure Semantics

Information regarding the this concept is available [here](broken-reference).

### Ecosystem Interfaces

To make the above sound less abstract, here are some parts of the protocol that we are seeing as potential standards or primitives for any future smart-contracts in our ecosystem to rely on:

* Doctor Certificate — the standard describing the structure of a tokenized non-transferable certificate to be used across the blockchain for credentials verification.
* &#x20;TBD

## Tokens

The protocol must utilize a native ERC-20 token(s) for governance, market transactions, incentives and other use cases featured in Tokenomics section.

## Federation

### SubDAOs

The protocol must provide infrastructure and interfaces for the existence of subDAOs — entities that are fairly autonomous and flexible in their governance and treasury management, while also being compliant with the core protocol standards and subjected to superDAO governance.

### SuperDAO

The protocol must have a single high-level DAO created during its genesis that would hold special governance privileges over any subDAO. The purpose of the superDAO is to act as an on-chain foundation, manage the core protocol treasury and develop the infrastructure mainly in a public goods funding fashion.

### SubDAO Factory

The protocol must support dynamic subDAO deployment on-chain with all the relevant genesis parameters.

## Escrow

### Overview

The protocol must have escrow functionality to be used across the ecosystem, with the primary focus on being a part of the core Knowledge Market mechanism in the MVP.

The exact use case examples are given in the sections below, while this section describes the escrow module in general.

### Escrow Parameters

Depending on the use case, the following parameters may be encoded or calculated dynamically to manage the escrow lifecycle.

#### Amount

The payment amount needed to complete the request is escrowed.

#### Time locks

Any kind of time lock that's either explicitly set or dynamically calculated. For example:

* Time delay before a market order get marked as stalled (for requester to reclaim the escrow);
* Time delay before the product or service performed by a DAO Member is considered delayed (for requester to reclaim the escrow).

#### Release Conditions

Any additional escrow release conditions.

#### Recipients & Fee Structure

The structure describing the escrow release distribution between various recipients in the protocol. For example:

* 90% to the treasury of the SubDAO that completed the order;
* 10% to the SuperDAO treasury (5% of this is the base fee as listed [here](../tokenomics/platform-v1.0/platform-usage-fees.md));
* 0% to the Requester .

### Escrow Triggers

The protocol should use escrow automatically to secure funds in specific use cases when necessary.

### Escrow Release

The protocol should use escrow automatically to release funds in specific use cases when necessary.

## Market

{% hint style="warning" %}
It is debatable whether or not the entire market functionality should be a part of the on-chain functionality.

Most of its MVP features can reasonably exist in a web2 space as long as the critically important history is saved on-chain.

Assuming that the pros of having it on-chain _might_ outweigh cons if it's done on Layer 2, we'll leave this section in the protocol spec for now.

The discussion is more than open.
{% endhint %}

### Market Mechanism

The proposed market mechanism resembles the classic freelance exchange bidding model with added crypto security and decentralization.

The proposed order lifecycle roughly looks like this:

* A \[new] requester creates a Knowledge Request (KR) — the request for MedDAO to deliver value in the form of product or service based on providing knowledge.
* A new order is registered on the market;
* A pre-defined payment amount is escrowed by the protocol;
* Based on the order category, all relevant subDAOs are notified;
* If the order never gets finalized after a pre-defined time delay, the requester can closed it and claim the escrow back.
* The requester can edit the order.
* A DAO Member can bid on the order with adjusted payment price.
* The requester can accept a bid which will result in the order being finalized.

### Finalizing Market Order

After the the market order is finalized, the Request For Knowledge associated with it is assigned to the winning bidder and the main RFK workflow begins.

## Knowledge Request (KR)

A Knowledge Request is the data structure that describes the unit of value containing the knowledge that is requested by a requester, produced by a subDAO, approved and delivered to the requester as a final product.

This section described the high-level structure of KR and how it evolves from a market order through the process of production to the final delivery.

### KR Structure

Every KR should have at least the following properties:

* Public data reference (e.g. URI)
* Private (encrypted) data references (e.g. URIs) for all kinds of off-chain data that is a part of the KR, such as:
  * Details provided by the requester;
  * Documents attached by the requester;
  * Knowledge provided by the assigned DAO Member;
* Case-specific parameters, such as:
  * Min count of approvals needed for the KR to pass the review stage.

### KR Access

KR files (stored off-chain and likely encrypted) would potentially contain sensitive patient data, so the access to them should be managed with caution and precision.

For this purpose it is proposed to associate all the addresses involved with a particular KR at the protocol level, and — combined with the role-based authorization — use this information as a gateway to any private data used in the application layer.

### KR Mutation

The same rules as above apply to KR mutation.

Any external transaction mutating the KR state must have a protocol-level guard logic checking the authorization level of the corresponding address.

### KR Lifecycle

The protocol must manage the lifecycle of the KR, ensuring proper transitions between its state based on the internal and external changes (effectively implementing a state machine).

#### Lifecycle Stages

The proposed (but revisable) stages in the KR lifecycle are:

* Registered — the KR is created externally and submitted in the protocol.
* Open — the KR is published on the market.
* Assigned — the KR is assigned to a DAO Member.
* In Review — the KR is awaiting approval or rejection by QA board.
* Complete — the KR is complete and the escrow is released.
* Rejected — the KR did not pass the QA review.

#### State Transitions

The following possible transitions between the KR lifecycle stages have been suggested based on the early protocol design discussion.

* —> Registered
  * This transition is triggered when an external address (user) creates a new KR in the system (e.g. posts a new market order).
* Registered —> Open
  * This transition is triggered when the public KR info (posted on the market) passes spam filter and is made accessible/biddable on the market.
  * The exact mechanism of filtration is yet to be defined and might be outside the MVP scope.
* Open —> Assigned
  * This transition is triggered when the KR is assigned to a DAO Member, likely as a result of an accepted market bid.
  * The protocol must ensure proper authorization checks when performing this transition.
* Assigned —> In Review
  * This transition is triggered when the KR is substantially complete and is ready for quality assurance / review.
  * The protocol must ensure proper authorization checks when performing this transition.
* In Review —> Complete
  * This transition is triggered when the KR passes the final review stage and is ready to be released and delivered to the requester.
  * The protocol must ensure proper authorization checks when performing this transition.
* In Review —> Rejected
  * This transition is triggered when the KR fails the final review and is awaiting resolution.
  * The protocol must ensure proper authorization checks when performing this transition.

## Governance

information regarding the treasury operations of MedDAO and its subDAOs can be found using the link below:

{% hint style="info" %}
Information regarding the governance operations of MedDAO and its subDAOs can be found using the link below:
{% endhint %}

{% content-ref url="broken-reference" %}
[Broken link](broken-reference)
{% endcontent-ref %}

## Treasury Management

{% hint style="info" %}
Information regarding the treasury operations of MedDAO and its subDAOs can be found using the link below:
{% endhint %}

{% content-ref url="../dao-governance/treasury-management.md" %}
[treasury-management.md](../dao-governance/treasury-management.md)
{% endcontent-ref %}
