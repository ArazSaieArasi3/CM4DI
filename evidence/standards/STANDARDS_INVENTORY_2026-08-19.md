# CM4DI Journal V2 — Normative Standards Inventory

**Cut-off date:** 2026-08-19  
**Scope:** Issue #3 / D05–D07  
**Method:** Primary/authoritative sources only; current stable specifications are the normative baseline, while active drafts are tracked separately as emerging evidence.

## Classification

- **Core candidate evidence** — supports a cross-paradigm concept or relation that may belong in CM4DI Core.
- **Profile evidence** — important but ecosystem/protocol-specific; should normally remain in a CM4DI profile.
- **Mapping evidence** — useful to map implementations/protocol artifacts onto neutral concepts without importing their vocabulary into Core.
- **Evaluation evidence** — useful primarily for scenarios, conformance, or test design.
- **Monitor** — relevant active draft or revision that is not yet a stable baseline.

## ISO/IEC

| Standard | Current status | Main ontology-relevant content | CM4DI use |
|---|---|---|---|
| ISO/IEC 24760-1:2025 | Published, Ed. 3 | identity, identifier, identity information, attributes, identity-management terminology | Core candidate evidence |
| ISO/IEC 24760-2:2025 | Published, Ed. 2 | reference architecture; individuals, organizations, devices, software; mobile/federated/decentralized identity | Core + profile evidence |
| ISO/IEC 24760-3:2025 | Published, Ed. 2 | identity information, attribute-based access, assurance practice | Core + Trust/Assurance profile |
| ISO/IEC 29115:2013 | Published; to be revised | entity-authentication assurance; four LoAs; mapping assurance schemes | Trust/Assurance profile; Monitor replacement |
| ISO/IEC 29146:2024 | Published, Ed. 2 | access management, subject, ICT resource, context, accountability | Core authorization evidence |
| ISO/IEC 23220-1:2023 | Published | mobile eID architecture and lifecycle phases | Wallet/mobile-ID profile |
| ISO/IEC TS 23220-2:2026 | Published, Ed. 2 | mobile eID data objects and generic exchange models | Wallet/mobile-ID profile |
| ISO/IEC TS 23220-3:2026 | Published | installation, issuing and deriving attributes/credentials, discoverability | Wallet/mobile-ID lifecycle profile |
| ISO/IEC TS 23220-4:2026 | Published | operational phase, issuer authentication, mdoc authentication, holder verification | Wallet/mobile-ID profile |
| ISO/IEC CD TS 23220-5 | Committee Draft, stage 30.92 | trust models and confidence-level assessment | Monitor; Trust/Assurance profile candidate |
| ISO/IEC 18013-5:2021 | Published; to be revised | mDL holder binding, reader, issuer, origin authentication, integrity | Wallet/mdoc mapping/profile |

### ISO supersession notes

- ISO/IEC 24760-1:2025 supersedes the withdrawn 2019 edition and its 2023 amendment.
- ISO/IEC 24760-2:2025 supersedes ISO/IEC 24760-2:2015.
- ISO/IEC TS 23220-2:2026 supersedes the withdrawn 2024 edition.
- ISO/IEC 29115:2013 remains current but ISO records it as **to be revised** by ISO/IEC CD 29115.2.
- ISO/IEC 18013-5:2021 remains published but is recorded as **to be revised**.

## NIST Digital Identity Guidelines

| Standard | Current status | Main ontology-relevant content | CM4DI use |
|---|---|---|---|
| NIST SP 800-63-4 | Final, Jul 2025 | identity proofing, enrollment, authenticators, authentication, federation, assertions, wallets | Core + profiles |
| NIST SP 800-63A-4 | Final, Jul 2025 | Applicant, Identity Evidence, identity proofing, CSP, enrollment, IAL | Strong Core candidate evidence |
| NIST SP 800-63B-4 | Final, Jul 2025 | Claimant, Subscriber, Authenticator, authentication, authenticator management, AAL | Core + Assurance profile |
| NIST SP 800-63C-4 | Final, Jul 2025 | federation, assertions, CSP/IdP, RP, subscriber attributes, FAL, wallets | Core federation candidates + profile |

The Revision 4 suite superseded the Revision 3 / 2020-updated family. The four current publications have persistent NIST DOIs and are treated as high-authority evidence.

## W3C

| Specification | Current status | Main ontology-relevant content | CM4DI use |
|---|---|---|---|
| Verifiable Credentials Data Model v2.0 | Recommendation, 15 May 2025 | Issuer, Holder, Verifier, VC, Credential Subject, Presentation, status | Wallet/VC profile; selected Core evidence |
| Decentralized Identifiers v1.0 | Recommendation, 19 Jul 2022 | DID, DID Subject, Controller, DID Document, Verification Method | Wallet/VC profile; Identifier/Subject evidence |
| Decentralized Identifiers v1.1 | Candidate Recommendation, 5 Mar 2026 | evolving DID model | Monitor; do not use as sole stable baseline |
| Verifiable Credential Data Integrity 1.0 | Recommendation, 15 May 2025 | cryptographic proof, verification methods, integrity/authenticity | Wallet/VC profile |
| Controlled Identifiers v1.0 | Recommendation, 15 May 2025 | controlled identifier, controller document, verification methods, services | Wallet/VC profile; controller/identifier distinction |
| Bitstring Status List v1.0 | Recommendation, 15 May 2025 | suspension/revocation/status information | Generic lifecycle evidence + VC profile |
| Web Authentication Level 2 | Recommendation, 8 Apr 2021 | public-key credential, authenticator, RP, user agent, attestation/assertion | Authentication profile + Core authenticator evidence |
| Web Authentication Level 3 | Candidate Recommendation, 26 May 2026 | evolved WebAuthn model | Monitor |
| Digital Credentials API | Working Draft, 1 Jun 2026 | browser/user-agent mediated credential issuance and presentation | Monitor; application/profile mapping |

Stable W3C Recommendations are used as the evidence baseline. Candidate Recommendations and Working Drafts are retained only to detect emerging semantic changes.

## OpenID Foundation

| Specification | Current status | Main ontology-relevant content | CM4DI use |
|---|---|---|---|
| OpenID Connect Core 1.0 + Errata Set 2 | Final, Dec 2023 | OP, RP, End-User, Subject Identifier, ID Token, Claims | Enterprise/Federated profile |
| OpenID Connect Session Management / Logout family | Final, Sep 2022 | session state, login status, logout | Enterprise/Federated profile |
| OpenID for Verifiable Presentations 1.0 | Final, Jul 2025 | credential presentation request/response, verifier, wallet | Wallet/VC profile |
| OpenID for Verifiable Credential Issuance 1.0 | Final, Sep 2025 | credential issuer, wallet, offer/request/issuance flow | Wallet/VC profile |
| OpenID4VC High Assurance Interoperability Profile 1.0 | Final, Dec 2025 | profiles OID4VCI/OID4VP with SD-JWT VC and ISO mdoc | Cross-standard mapping + assurance profile |
| OpenID Federation 1.1 | Final, May 2026 | federation entity, entity statement/configuration, trust chain, trust anchor, federation policy | Federation + Trust profile; selected Core candidates |
| OpenID Federation for OpenID Connect 1.1 | Final, May 2026 | application of federation trust to OIDC | Enterprise/Federated profile |
| Authorization API 1.0 (AuthZEN) | Final, Jan 2026 | Subject, Resource, Action, Context, Decision, PDP, PEP | Strong Core authorization evidence |
| OpenID Connect for Identity Assurance 1.0 | Final; 2026 errata activity | verified claims, identity-assurance evidence/process metadata | Trust/Assurance profile; monitor errata |

## IETF

| RFC | Status | Main ontology-relevant content | CM4DI use |
|---|---|---|---|
| RFC 6749 / RFC 6750 | Standards Track foundations; updated by current BCPs | OAuth roles, authorization grant, access token | Mapping/profile, not Core vocabulary source by itself |
| RFC 9700 | BCP 240, Jan 2025 | current OAuth 2.0 security best practice | Mapping/evaluation |
| RFC 7519 | Proposed Standard | JWT and name/value Claims; issuer, subject, audience | Mapping; semantic Claim comparison |
| RFC 7643 | Proposed Standard; updated | SCIM User/Group resources, attributes, schema | Enterprise provisioning profile |
| RFC 7644 | Proposed Standard; updated | create/modify/retrieve/delete identity resources | Lifecycle/provisioning profile |
| RFC 9865 | Proposed Standard, Oct 2025 | cursor pagination updates to SCIM | Mapping-only |
| RFC 9967 | Proposed Standard, May 2026 | SCIM provisioning/security events; create/patch/put/delete/activate/deactivate | Lifecycle-event evidence |
| RFC 8693 | Proposed Standard | security token exchange, subject/actor, impersonation/delegation | Enterprise/Federated profile; delegation candidate |
| RFC 10017 | BCP, Jul 2026 | OAuth for browser-based applications | Evaluation/mapping only |

## OASIS

| Standard | Status | Main ontology-relevant content | CM4DI use |
|---|---|---|---|
| SAML 2.0 | OASIS Standard, 2005; errata maintained | Assertion, authentication/attribute/authorization statements, IdP/SP federation | Enterprise/Federated profile; Assertion distinction |
| XACML 3.0 + Errata 01 | OASIS Standard | Subject, Resource, Action, Environment/attributes, Request, Decision, Policy, Rule, Obligation, Advice, PDP, PEP | Strong authorization evidence |
| JSON Profile of XACML 3.0 v1.1 | OASIS Standard, Jun 2019 | representation-independent PEP↔PDP request/response | Authorization mapping/evaluation |

## FIDO Alliance

| Specification | Current status | Main ontology-relevant content | CM4DI use |
|---|---|---|---|
| FIDO2 / CTAP 2.3 | Proposed Standard, 2026 | client platform, authenticator, public-key credential, user verification | Authentication profile |
| WebAuthn Level 2 (referenced by FIDO2) | W3C Recommendation | RP-scoped credentials, authenticators, attestation/assertion | Authentication profile |
| CTAP 2.3.1 | Working Draft, May 2026 | emerging CTAP maintenance | Monitor only |

## Coverage conclusion

The inventory covers all standards-development organizations explicitly required by Issue #3: **ISO/IEC, NIST, W3C, IETF, OASIS, OpenID Foundation and FIDO Alliance**. It intentionally does not attempt to enumerate every cryptographic algorithm, token format extension, niche profile, or vendor configuration. Such items are added only when they introduce a materially distinct identity concept, lifecycle event, trust relation, or evaluation need.

## Immediate implications for CM4DI

1. **Identity Evidence** and **Identity Proofing** are strong missing concept/event candidates, distinct from Enrollment.
2. **Federation** and **Assertion** need explicit treatment; an assertion cannot be safely collapsed into Claim.
3. Current **Authorization** is too thin for cross-standard coverage: Resource, Action, Context and Decision semantics are strongly supported by ISO/IEC 29146, XACML and AuthZEN.
4. **Credential lifecycle/status** needs generic semantics (issuance, suspension, revocation, activation/deactivation where appropriate), while concrete mechanisms remain profiles.
5. **Session** is an Enterprise/Federated profile candidate, not yet a Core recommendation.
6. **Trust Anchor / Trust Chain / Federation Policy** are strong Trust/Federation profile candidates and will be tested against government trust frameworks in Issue #4.
7. **Holder**, **Subscriber**, **Claimant**, **Applicant**, **Controller**, **Actor**, and **Principal/Subject** must not be merged merely because they can refer to the same real-world party in a scenario; their role semantics differ.
8. Protocol syntax constructs such as JWT, access token, CTAP messages and specific VC status encodings remain mapping/profile artifacts unless later evidence establishes a cross-paradigm ontological need.

## Primary-source rule

Every retained item above was verified against an official SDO/institutional source. Secondary summaries are not evidence for ontology admission decisions.