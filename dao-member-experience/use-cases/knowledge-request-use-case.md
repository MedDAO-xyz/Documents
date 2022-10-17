# Knowledge Request Use Case

## Overview

Knowledge Requests (KRs) are one of the proposed use cases of MedDAO and its members. At inception the platform will support Industry KRs. In the future, we plan to expand KR use cases to include legal, government, research and other areas developed by subDAOs.

Our hope is that members of MedDAO and its subDAOs will come up with new & novel KR use cases that provide value to the community. In this event, members can submit a [proposal](../../dao-governance/proposals.md) for new KR use cases to the appropriate subDAO.

Guidelines for what should be included in the proposal:&#x20;

* Details about the new use cases&#x20;
* Platform Usage Fee Structure&#x20;
* Funds needed to develop, test and roll out the new use case

{% hint style="info" %}
For more information on subDAOs within MedDAO please click [here](../../dao-governance/governance-structure.md#subdaos)
{% endhint %}

## Completing Order

{% embed url="https://www.figma.com/file/rGWNUC8e8JLqSpGMxkFwjN/Knowledge-Request-Module-V1?node-id=0:1" %}



## Compensation

The breakdown of platform usage fees for services rendered are established by each subDAO for each KR type. This includes:

1. Percentage allocated to the MedDAO Treasury
   * This cannot be lower than the established MedDAO global minimum, though a subDAO can set this at a higher rate
2. Percentage allocated to the subDAO Review Board
   * This is to incentive the work done by members of the Review Board
3. Percentage allocated to the subDAO’s Treasury
4. SubDAO may identify other entities to allocate fee percentages

#### **Changing MedDAO Treasury Take Rate**

MedDAO establishes a global minimum take rate for all services rendered through the KR platform which goes directly to the MedDAO multisig treasury. Currently the minimum take rate is 5%. Changes to this can be made through the [Formal Proposal](../../dao-governance/proposals.md#formal-proposals) process.

## SubDAO Knowledge Request Review Board

A critical component of the KR platform process includes review of submitted work on a KR by a subDAO contributor. The subDAO Review Board is responsible for determining the quality of the work and whether it meets the criteria outlined by the KR requester to a satisfactory degree.

### Serving on a Review Board:

SubDAOs should determine:

1. The criteria for who can serve on the Review Board, including whether this is an elected position, or a bounty open to all subDAO contributors.
   * If a subDAO determines this should be an elected position, they must define:
     * [ ] Criteria for election
     * [ ] Process for election
     * [ ] Terms for each election
2. The number of users who should serve on the Review Board

### Reviewing Submitted Work**:**

As the Review Board is responsible for approving or rejecting the work submitted by a subDAO contributor for a KR request, subDAOs should determine:

1. The number of users needed for the Review Board&#x20;
2. The criteria for approving or rejecting work submitted, including the voting process and minimum votes needed to pass
   * In the case of rejection, the Review Board is responsible for giving enough feedback needed for the contributor to modify their work towards a KR

## Governance

**The following are activities related to the KR Platform that involve governance:**

1. Changes to MedDAO take rates for services rendered&#x20;
2. KR Platform Usage Fee Structure&#x20;
3. New KR use cases&#x20;
4. SubDAO Review Board
   * Elections/Criteria to serve&#x20;
   * Approval or rejection work submitted for a KR by a subDAO contributor

## **First Expected Knowledge Request Implementation - Medical Industry**

{% hint style="warning" %}
At inception MedDAO will support Industry Knowledge Requests due to the legal implications of engaging directly with patients and other stakeholders in the medical space.
{% endhint %}

Examples of medical industry include medical device manufacturers, pharmaceutical companies, etc.

In the future, we plan to expand Knowledge Request use cases to include patients, legal, government, research and other areas submitted by subDAOs.

### **Example Use Case for an Industry User interacting with the MedDAO Platform**

1. The industry user accesses the platform
2. They access the knowledge request form and input the request
3. They are presented with a knowledge request cost
   * This cost will be calculated based on active users in the system and number of Knowledge requests being worked on
   * If rejected, they can wait to submit later
4. Upon acceptance, the amount of the payment required for the Knowledge request will be escrowed and the Knowledge Request submitted
5. The Knowledge request will be presented to the appropriate subDAO
   * If subDAO contributors do not pick up the Knowledge request in a reasonable amount of time, the Knowledge Request will be canceled, and funds returned
6. A subDAO contributor will accept the knowledge request and start working on it
7. The contributor completes the Knowledge Request and submits it for review
8. The subDAO review board will review the request
   * If rejected, the Knowledge Request is sent back to the contributor for review
9. Upon subDAO review board approval, the Knowledge Request is sent to the subDAO for approval
   * If rejected, the Knowledge Request is sent back to the contributor for review
10. Upon subDAO approval, the completed Knowledge Request is sent to the user
    * The user will have the option to complete a user feedback form
11. The payment is then released to the DAO, to be distributed to the subDAO, subDAO review board, and contributor

## Future Considerations

MedDAO has begun contemplating what future iterations of a Knowledge request could look like, with more of a focus on quality control, timeliness of request fulfillment, and more.

{% embed url="https://www.figma.com/file/8Uhy9NQ4bvQX0RcOxewGgD/Knowledge-Request-Platform-V1.1" %}



### **Knowledge Request User Dispute Automation**

* If a user disputes what they received from a knowledge request, they will be able to interact with the platform to initiate a processes to enable a resolution of the issue

### Time-based Penalties

* Create a penalty layer to ensure that subDAO members are responding to requests in a timely manor

### Patient Facing Use Case

* In today's world a patient goes to their doctor and receives one doctors opinion, using the knowledge request model MedDAO expects patients will be able to acquire multiple medical opinions from medical professionals (with the correct expertise) to discover all their options as well as gain a consensus of opinion as to how they should proceed
