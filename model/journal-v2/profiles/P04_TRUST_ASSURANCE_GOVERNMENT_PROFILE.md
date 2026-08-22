# P04 — Trust / Assurance / Government Profile

## Purpose
Represent governed trust ecosystems, government digital identity, assurance frameworks, registries and conformity mechanisms while keeping Core trust semantics small and neutral.

## Core reuse
- P04 `TrustFramework`, `TrustRegistry`, `TrustedList`, `TrustAnchor` and `TrustChain` are explicitly distinct from Core `TrustAssessment`.
- Framework-specific IAL/AAL/FAL or national confidence levels map to Core `AssuranceAssessment` dimensions and values rather than replacing the Core concept.
- `LegalIdentity`, `PersonIdentificationData` and `GovernmentAttestation` are profile constructs that may ground or represent identity information about a Core `IdentitySubject`.
- Certification, accreditation and ecosystem participation have governance lifecycles distinct from Core `Enrollment`, `CredentialStatus` and authentication.
- Core `TrustReference` is an alignment hook, not a generic container for all P04 concepts.

## Profile concepts
P04 contributes 18 governed concepts: TrustFramework, GovernanceFramework, TrustRegistry, TrustedList, TrustAnchor, TrustChain, GovernanceAuthority, Registrar, Regulator, ConformityAssessmentBody, Certification, Accreditation, EcosystemParticipation, ParticipantStatus, LegalIdentity, PersonIdentificationData, GovernmentAttestation and IdentityServiceProvider.

## Representative external alignments
- NIST SP 800-63 Rev.4: IAL/AAL/FAL -> dimension-specific Core `AssuranceAssessment`; CSP/IdP/RP functions map to contextual roles and profile provider constructs rather than rigid Core kinds.
- eIDAS 2.0 / EUDI Wallet: trust framework/provider status -> P04 governance constructs; PID/EAA -> `PersonIdentificationData`/`GovernmentAttestation` + Core `Credential`; wallet interaction itself remains P02.
- UK Digital Identity and Attributes Trust Framework / GPG45: provider registration/certification -> P04 `EcosystemParticipation`/`Certification`; identity confidence -> Core `AssuranceAssessment`; orchestration/intermediary maps jointly with P01 `IdentityBroker`/intermediary pattern where appropriate.
- Pan-Canadian Trust Framework and Australian digital-ID governance: framework/participant/provider/assessment statuses map to P04 concepts with jurisdiction-specific specializations only when necessary.
- OpenID Federation: TrustAnchor/TrustChain -> P04 technical-trust constructs; federation relationship itself remains P01.
- SPIFFE Trust Domain/Bundle remain P03 constructs and are related to—not subclasses of—P04 TrustFramework/Registry semantics.

## Anti-conflation invariants
`TrustAssessment != TrustFramework`; `TrustRegistry != TrustAnchor`; `TrustedList != TrustChain`; `Certification != Accreditation`; `EcosystemParticipation != Enrollment`; `ParticipantStatus != CredentialStatus`; `LegalIdentity != DigitalIdentity`; `PID != IdentityAttribute`; `GovernmentAttestation != LegalIdentity`; `GovernanceAuthority != IdentityProvider`; `cryptographic validation != institutional conformance`.

## Minimum scenario
A person plays Core `IdentitySubject`; a government/legal process establishes a P04 `LegalIdentity` basis and `PersonIdentificationData`; a regulated provider issues a P04 `GovernmentAttestation`/Core `Credential`; a dimension-specific `AssuranceAssessment` records proofing/authentication assurance; the provider participates in an `EcosystemParticipation` governed by a `TrustFramework`, with certification/status exposed through a `TrustRegistry` or `TrustedList` while Core `TrustAssessment` remains a distinct evaluative artifact.

## Wave-7 formalization expectation
P04 imports the Core and may reference P02/P01 profile concepts through explicit module mappings. Legal and jurisdiction-specific terms remain profile specializations; no national or EU framework becomes the ontology Core.