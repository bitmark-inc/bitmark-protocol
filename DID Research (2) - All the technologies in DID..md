---
title: DID Research (2) - All the technologies in DID.
description: 統整所有的 did 文獻、方法
tags: DID, @doge 
robots: noindex, nofollow
---

# DID Research (2) - All the technologies in DID.
> Author[name=@doge]
> [time=Wed, May 19, 2021 3:37 PM]

[TOC]

* [https://w3c-ccg.github.io/universal-wallet-interop-spec/](https://w3c-ccg.github.io/universal-wallet-interop-spec/) 
* [https://www.abtwallet.io/zh/](https://www.abtwallet.io/zh/) 
* [https://booster.registry.arcblock.io/](https://booster.registry.arcblock.io/) 
* [https://www.didconnect.io/en/](https://www.didconnect.io/en/) 
* [https://bloksec.com/](https://bloksec.com/) 
* [https://ceramic.network/](https://ceramic.network/) 
* [https://github.com/transmute-industries/did-wallet](https://github.com/transmute-industries/did-wallet) 
* [https://www.transmute.industries/](https://www.transmute.industries/) 
* [https://github.com/decentralized-identity/element/blob/master/docs/did-method-spec/spec.md](https://github.com/decentralized-identity/element/blob/master/docs/did-method-spec/spec.md) 
* [https://internetidentityworkshop.com/past-workshops/](https://internetidentityworkshop.com/past-workshops/) 
* [https://www.weboftrust.info/specs.html](https://www.weboftrust.info/specs.html)

## DID入門

* [https://github.com/WebOfTrustInfo/rwot5-boston/blob/master/topics-and-advance-readings/did-primer.md](https://github.com/WebOfTrustInfo/rwot5-boston/blob/master/topics-and-advance-readings/did-primer.md)

## DID

* [https://github.com/WebOfTrustInfo/rwot6-santabarbara/blob/master/final-documents/did-spec-1.0.md](https://github.com/WebOfTrustInfo/rwot6-santabarbara/blob/master/final-documents/did-spec-1.0.md)

1. The DID method name.
2. The ABNF structure of the method-specific identifier.
3. How the method-specific identifier is generated or derived.
4. How the *[CRUD operations](https://en.wikipedia.org/wiki/Create,_read,_update_and_delete)* are performed on a DID and DID document:
![](https://hackmd.io/_uploads/HkwM64MY_.png)
    a. **Creating** a new DID.
    b. **Reading** (resolving) a DID document.
    c. **Updating** a DID document.
    d. **Deleting** (revoking) a DID.

## OP - OpenID Connect Identity Provider. An entity that issues authentication-related assertions (such as ID Tokens).

## SIOP - Self-Issued OpenID Connect Provider. A personal, self-hosted Identity Provider that issue self-signed assertions.

* [https://openid.net/specs/openid-connect-core-1_0.html](https://openid.net/specs/openid-connect-core-1_0.html)

## WalletConnect Documentation

* [https://github.com/WalletConnect/walletconnect-docs](https://github.com/WalletConnect/walletconnect-docs)

## Verifiable Credentials Use Cases

* [https://w3c.github.io/vc-use-cases/](https://w3c.github.io/vc-use-cases/)

![](https://hackmd.io/_uploads/r1vSa4ztd.png)
![](https://hackmd.io/_uploads/ByKBTVMtu.png)
![](https://hackmd.io/_uploads/rk3S64zYu.png)



## RP - Relying Party, an application or service that relies on the Identity Provider's assertions.

## DID TLS

## DID Names

## DDID: Derived DID

## DDO:DID Document

1. **The DID itself**, so the DID document is fully self-describing.
2. **A set of public keys or other proofs** that can be used for authentication or interaction with the identified entity.
3. **A set of service endpoints** that describe where and how to interact with the identified entity.
4. **A set of authorized capabilities** for the identified entity -- or other delegated entities -- to make changes to the DID document.
5. **Timestamps** for auditing.
6. **A optional JSON-LD signature** if needed for verifying the integrity of the document.

## 巴科斯範式(BNF/EBNF)定義語言

* [https://hackmd.io/@ShenTengTu/HJzCM3aDr](https://hackmd.io/@ShenTengTu/HJzCM3aDr)

## DAD:Decentralized Autonomic Data

* [https://github.com/WebOfTrustInfo/rwot6-santabarbara/blob/master/final-documents/DecentralizedAutonomicData.md](https://github.com/WebOfTrustInfo/rwot6-santabarbara/blob/master/final-documents/DecentralizedAutonomicData.md)
* [https://github.com/WebOfTrustInfo/rwot7-toronto/blob/master/topics-and-advance-readings/ZeroTrustComputingWithDidsAndDads.md](https://github.com/WebOfTrustInfo/rwot7-toronto/blob/master/topics-and-advance-readings/ZeroTrustComputingWithDidsAndDads.md)

## DADi：Decentralized Autonomic Data (DADi) items

## Quantum Secure DIDs

* [https://github.com/WebOfTrustInfo/rwot10-buenosaires/blob/master/final-documents/quantum-secure-dids.md](https://github.com/WebOfTrustInfo/rwot10-buenosaires/blob/master/final-documents/quantum-secure-dids.md)

## RDF ：Resource Description Framework
* [https://www.w3.org/TR/rdf11-concepts/](https://www.w3.org/TR/rdf11-concepts/)

## ID Hub

* [https://github.com/WebOfTrustInfo/rwot6-santabarbara/blob/master/final-documents/identity-hub-attestations.md](https://github.com/WebOfTrustInfo/rwot6-santabarbara/blob/master/final-documents/identity-hub-attestations.md)

## DID Auth

* [https://github.com/WebOfTrustInfo/rwot6-santabarbara/blob/master/final-documents/did-auth.md](https://github.com/WebOfTrustInfo/rwot6-santabarbara/blob/master/final-documents/did-auth.md)

## SSI： Self-Sovereign Identity

* [https://github.com/WebOfTrustInfo/rwot6-santabarbara/blob/master/final-documents/a-roadmap-for-ssi.md](https://github.com/WebOfTrustInfo/rwot6-santabarbara/blob/master/final-documents/a-roadmap-for-ssi.md)

## 機構

- RWOT：Rebooting Web of Trust [http://www.weboftrust.info/](http://www.weboftrust.info/)
- IIW：Internet Identity Workshop [https://www.internetidentityworkshop.com/](https://www.internetidentityworkshop.com/)
- W3C：
    - [World Wide Web Consortium (W3C)](https://www.w3.org/) is an international community that develops open standards to ensure the long-term growth of the Web. Two working groups are particularly relevant to self-sovereign identity:
    - [Verified Claims Working Group (VC)](https://www.w3.org/2017/vc/WG/) seeks to make it easier and more secure to express and exchange credentials on the web that have been verified by a third party.
    - [Credentials Community Group (CCG)](https://www.w3.org/community/credentials/) explores the creation, storage, presentation, verification, and user control of credentials. The group drafts and incubates internet specifications for further standardization and prototyping and tests reference implementations. CCG was the original source of material for the official Verified Claims Working Group.
- DIF：Distributed Identity Foundation [http://identity.foundation/](http://identity.foundation/)
- ITEGA：Information Trust Exchange Governing Association [https://infotrust.org/](https://infotrust.org/)

## OB：Open Badge   VC：Verifiable Credentials

* [https://github.com/WebOfTrustInfo/rwot6-santabarbara/blob/master/final-documents/open-badges-are-verifiable-credentials.md](https://github.com/WebOfTrustInfo/rwot6-santabarbara/blob/master/final-documents/open-badges-are-verifiable-credentials.md)

## dpki

* [https://github.com/WebOfTrustInfo/rwot7-toronto/blob/master/topics-and-advance-readings/dids-in-dpki.md](https://github.com/WebOfTrustInfo/rwot7-toronto/blob/master/topics-and-advance-readings/dids-in-dpki.md)

## dkms

## **wallet design**
* [https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-130.pdf](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-130.pdf)
* [https://github.com/hyperledger/indy-sdk/blob/677a0439487a1b7ce64c2e62671ed3e0079cc11f/doc/design/005-dkms/DKMS Design and Architecture V3.md](https://github.com/hyperledger/indy-sdk/blob/677a0439487a1b7ce64c2e62671ed3e0079cc11f/doc/design/005-dkms/DKMS%20Design%20and%20Architecture%20V3.md)
* [https://github.com/hyperledger/aries-rfcs/blob/master/concepts/0051-dkms/dkms-v4.md](https://github.com/hyperledger/aries-rfcs/blob/master/concepts/0051-dkms/dkms-v4.md)
* [https://hyperledger-indy.readthedocs.io/projects/sdk/en/latest/docs/design/005-dkms/README.html](https://hyperledger-indy.readthedocs.io/projects/sdk/en/latest/docs/design/005-dkms/README.html)
* [https://github.com/WebOfTrustInfo/rwot1-sf/blob/master/draft-documents/Decentralized-Public-Key-Infrastructure-CURRENT.md](https://github.com/WebOfTrustInfo/rwot1-sf/blob/master/draft-documents/Decentralized-Public-Key-Infrastructure-CURRENT.md)
* [https://github.com/hyperledger/indy-sdk/tree/master/docs/design/005-dkms](https://github.com/hyperledger/indy-sdk/tree/master/docs/design/005-dkms)

## wallet design
* [https://www.slideshare.net/SSIMeetup/the-state-of-digital-identity-wallets-darrell-odonnell](https://www.slideshare.net/SSIMeetup/the-state-of-digital-identity-wallets-darrell-odonnell)

## auth
* [https://www.slideshare.net/SSIMeetup/introduction-to-did-auth-with-markus-sabadello](https://www.slideshare.net/SSIMeetup/introduction-to-did-auth-with-markus-sabadello)

## Zero-Knowledge Proofs:
* [https://www.slideshare.net/SSIMeetup/zeroknowledge-proofs-privacypreserving-digital-identity-with-clare-nelson](https://www.slideshare.net/SSIMeetup/zeroknowledge-proofs-privacypreserving-digital-identity-with-clare-nelson)
* [https://www.ockam.io/team](https://www.ockam.io/team)
* [https://github.com/ockam-network/ockam](https://github.com/ockam-network/ockam)
* [https://www.slideshare.net/SSIMeetup/machine-identity-dids-and-verifiable-credentials-for-a-secure-trustworthy-and-interoperable-iot-mrinal-wadhwa](https://www.slideshare.net/SSIMeetup/machine-identity-dids-and-verifiable-credentials-for-a-secure-trustworthy-and-interoperable-iot-mrinal-wadhwa)
* [https://github.com/WebOfTrustInfo/rwot7-toronto/blob/master/final-documents/A_DID_for_everything.md](https://github.com/WebOfTrustInfo/rwot7-toronto/blob/master/final-documents/A_DID_for_everything.md)

![](https://hackmd.io/_uploads/BkJLpNzFd.png)
![](https://hackmd.io/_uploads/HkM8TEfKd.png)

## 共享個人健康數據以改善慢性病的治療
* [https://github.com/WebOfTrustInfo/rwot10-buenosaires/blob/master/topics-and-advance-readings/use_case_sharing_personal_health_data_to_improve_treatment_of_chronic_conditions.md](https://github.com/WebOfTrustInfo/rwot10-buenosaires/blob/master/topics-and-advance-readings/use_case_sharing_personal_health_data_to_improve_treatment_of_chronic_conditions.md)

鑰匙:seed, key

控制器：DID, DID Doc, DKMS, Tx, Contract, 

目標：鏈, Service