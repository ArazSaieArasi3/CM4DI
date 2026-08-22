# P04 — Governed Identity Profile

**Legacy label:** Trust / Assurance / Government  
**DDD status:** Cross-domain integration Profile; not a Domain or Bounded Context.

## Purpose
Represent governed trust ecosystems, government digital identity, assurance frameworks, registries and conformity mechanisms while keeping Identity Evidence, Trust Governance and Government Identity semantically distinct.

## Domain composition
P04 composes Identity Representation, Identity Information, Identity Evidence, Identity Establishment, Credential Management, Trust Governance and Government Identity.

## Domain reuse
- `TrustFramework`, `TrustRegistry`, `TrustedList`, `TrustAnchor` and `TrustChain` belong to Trust Governance and are distinct from `TrustAssessment`.
- Framework-specific IAL/AAL/FAL or national confidence levels map to Identity Evidence `AssuranceAssessment` dimensions/values rather than replacing the concept.
- `LegalIdentity`, `PersonIdentificationData`, `GovernmentAttestation` and governed `IdentityServiceProvider` belong to Government Identity.
- Certification, accreditation and ecosystem participation belong to Trust Governance and have lifecycles distinct from Identity Establishment `Enrollment`, CredentialStatus and Authentication.
- `TrustReference` remains a Core alignment hook, not a generic container for all governance constructs.

## Profile concepts
P04 contributes 18 governed concepts distributed across Trust Governance and Government Identity. Primary Domain assignments are canonical in `../ddd/CONCEPT_DOMAIN_ASSIGNMENT_v2.csv`.

## Representative external alignments
- NIST SP 800-63 Rev.4: IAL/AAL/FAL -> dimension-specific `AssuranceAssessment`; provider functions map to contextual provider/interaction roles.
- eIDAS/EUDI: trust framework/provider status -> Trust Governance; PID/EAA -> Government Identity plus Credential Management; wallet interaction itself remains P02.
- UK Digital Identity and Attributes Trust Framework / GPG45: registration/certification -> Trust Governance; identity confidence -> Identity Evidence; intermediary interaction may compose Federation.
- Pan-Canadian and Australian governance: framework/participant/provider/assessment statuses map to Trust Governance with jurisdiction-specific specializations only when necessary.
- OpenID Federation: TrustAnchor/TrustChain -> Trust Governance; federation relationship remains Federation.
- SPIFFE TrustDomain/TrustBundle remain Workload Identity constructs and are related to, not subclasses of, Trust Governance structures.

## Anti-conflation invariants
`TrustAssessment != TrustFramework`; `TrustRegistry != TrustAnchor`; `TrustedList != TrustChain`; `Certification != Accreditation`; `EcosystemParticipation != Enrollment`; `ParticipantStatus != CredentialStatus`; `LegalIdentity != DigitalIdentity`; `PID != IdentityAttribute`; `GovernmentAttestation != LegalIdentity`; `GovernanceAuthority != IdentityProvider`; `cryptographic validation != institutional conformance`.

## Minimum scenario
Government identity establishment composes Identity Representation + Identity Evidence + Identity Establishment + Credential Management + Trust Governance + Government Identity. Credential presentation may additionally compose P02 without moving Wallet/Presentation into Government Identity.

## Wave-7 formalization expectation
Formal packaging follows Bounded Context ownership. Trust Governance and Government Identity are distinct contexts even when P04 presents them together. P04 itself is not automatically one OWL module.