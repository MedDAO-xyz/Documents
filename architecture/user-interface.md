# User Interface

## Protocol Layer

MedDAO application user interface (UI) must rely on MedDAO protocol standards, abstractions, primitives and tools to ensure compatibility across all the future applications in the ecosystem.

{% content-ref url="protocol.md" %}
[protocol.md](protocol.md)
{% endcontent-ref %}

## Platform Layer

It is suggested to extract as many reusable tools and components as possible from the application to the platform layer in order to improve maintainability and consistency of the future application ecosystem.

{% content-ref url="platform.md" %}
[platform.md](platform.md)
{% endcontent-ref %}

## Governance

The governance interface is to be defined. In the minimally viable product (MVP) we will most likely not require any custom UI for proposals and voting, and one of the existing industry standard tools is suggested.

### Browsing Proposals

TBD

### Creating a Proposal

TBD

### Voting on a Proposal

TBD

## Treasury Management

### Treasury wallet control

TBD

### Treasury transactions execution

TBD

## Authorization Level Management

### Assigning Authorization Level

The application must feature a UI to manually set authorization level for a given address in the protocol.

## KYC

### KYC Application & Completion

It is proposed to source the KYC completion and on-chain proof issuance interface from a 3rd party provider of the DAO's choice.&#x20;

## Credentials

### Credentials Verification Application & Completion

The application must feature a UI for the user to complete doctor credentials verification resulting in a non-transferable on-chain certificate minted to their address.

## Market

This section describes UI for the knowledge marketplace functionality of the MedDAO application.

### Browsing the Market

The application must feature a marketplace UI where anyone can browse orders permissionlessly.

### Creating an Order as a Requester&#x20;

A user must be able to submit a new Knowledge Request order on the market.&#x20;

### Editing an Order as a Requester&#x20;

A user must be able to update the details for an existing new Knowledge Request order on the market.&#x20;

### Spam Filter

TBD

### Reclaiming Escrow for a Stalled Order as a Requester&#x20;

A user must be able to close an order after a period of inactivity and reclaim the escrow funds back.

### Communication between a Requester and a DAO Member

It is proposed to use 3rd-party channels such as Discord to organize communication between the Requester and any DAO Member looking to proceed with the order and/or get more details.

### Bidding on an Order as a DAO Member

A user with a proper authorization role (DAO Member) must be able to bid on an existing market order. A suggested bid information would include the price in $MED and a free-form comment.

### Accepting a bid as a Requester

A user must be able to accept a bid on their existing active market order.

## Knowledge Request (KR) Workflow

This section describes UI for the knowledge request workflow and delivery process in MedDAO application.

### Browsing My KR History as a DAO Member or a Requester

A user must be able to view all the completed and in-progress knowledge requests they have access to, either as a Requester or as a DAO Member involved in the workflow.

### Viewing KR Details as a DAO Member or a Requester

A user must be able to open and view details of any completed and in-progress knowledge requests they have access to, either as a Requester or as a DAO Member involved in the workflow.

#### KR Structure

The knowledge request details displayed should reflect KR data that makes sense to the user based on their role, whether it's the requester, the main assigned DAO Member providing the knowledge, a quality assurance / approval board member, etc.

### Communication between a Requester and a DAO Member

It is proposed to exclude any custom communication tools from the initial version scope, and leave it up to the users or/and the DAO guidelines to determine the ways and channels of communication during the knowledge request workflow. An example would be a Discord thread.

### Updating KR Details as a Requester

A user must be able to make edits to certain details or attach documents to a knowledge request owned by them.

### Updating KR Response as a DAO Member

A user that has access to a particular knowledge request and has the appropriate authorization role must be able to add a response to such knowledge request in the following forms combined together:

* A text containing the summary / details of the response.
* A set of file attachments.

### Submitting KR for Review as a DAO Member

A user that has provided a response to a particular knowledge request and has the appropriate authorization role must be able to submit such response for review by the approval board.

### Submitting KR Review as a DAO Member

A user that is assigned to review a particular knowledge request and has the appropriate authorization role must be able to complete and submit their final review of such request.

A review must result in either of the two assigned statuses:

* Rejected
* Approved

If the review is rejected, a text comment with optional file attachments must be added to the rejection.&#x20;

## Knowledge Request (KR) Completion

### Reclaim Escrow for a Stalled KR as a Requester

A user that has created a particular knowledge request and has their payment for such request in escrow must be able to reclaim the funds back from escrow after a period of inactivity during one of the knowledge request's lifecycle stages:

* Market order — the escrow can be reclaimed if no bids were placed in a certain period of time.
* Knowledge request delivery — the escrow can be reclaimed if no updates were given / submitted by the assigned DAO Member(s) in a certain period of time.

### Provide feedback as a Requester

A user that has created a particular knowledge request and has received the final approved response to such request must be able to submit their feedback in the form of a free-form text.

###
