# MedCred

## Overview

The MedCred NFT is a non-transferrable NFT issued by an administrative function within MedDAO. The process for issuing this NFT is outlined in the governance of each subDAO.&#x20;

To start, MedCred will represent certification by MedDAO that the holder is a licensed practitioner in the subDAO’s field.&#x20;

In the future, this NFT can represent certification of anything a subDAO defines. For example, a MedCred NFT can be issued to patients who have received spinal surgeries in a spinal surgery patient subDAO.

The details and specifications of the MedCred NFT will be further defined by the engineering team.

## MedCred Certification

### Certification Authority

The protocol must define or support a mechanism for on-chain certificate issuance and revocation. Any address in the protocol could be granted an authorization level that makes it a Certification Authority, i.e. lets it issue or revoke certificates for any other address.

### Certificate

Every certificate must comply with a cross-protocol standard that makes it possible for any smart-contract to rely on it.

The primary purpose of a certificate is to serve as a non-transferable proof of off-chain credentials verification and protect the system against bad actors.

There's no strictly defined data structure proposed for the certificate standard at the moment, but it should feature data fields that reflect the validity of an off-chain document, such as expiration date.

### Issuing & Revoking Certificates

The protocol must support a way to issue or revoke tokenized certificates by a Certification Authority address.

## MedCred MVP Walkthrough

{% embed url="https://www.figma.com/file/fcZUQhKfN8Zl6Pr6NJlaVK/MedCred-v1?node-id=0:1" %}
