# CM4DI Journal V2 — Wave 5 Domain Decision Log

This log demonstrates completion of O01–O13 before the final UFO/anti-pattern freeze.

## O01 — Conference-model gap analysis — COMPLETE
Evidence-driven delta is documented in `evaluation/WAVE5_BASELINE_TO_V2_DELTA_2026-08-22.md`.

Key result: the largest semantic gaps were evidence/proofing/binding, minimal authorization semantics, role rigidity, trust overloading and human-centric assumptions.

## O02 — Competency-question registry — COMPLETE
`research/COMPETENCY_QUESTION_REGISTRY_v2.csv` defines 32 governed CQs with stable IDs, required concepts/relations, expected capability and evaluation targets, following OGCM-RF CQ metadata requirements.

## O03 — Core/Profile boundary — COMPLETE
`model/journal-v2/CORE_PROFILE_BOUNDARY_v2.md` fixes Minimal Core + P01/P02/P03/P04 and external/Social-Future boundaries.

## O04 — Party / IdentitySubject / human–non-human boundary — COMPLETE
Decision:
- `Party` = abstract `<<roleMixin>>` for participation in identity interactions.
- `IdentitySubject` = abstract `<<roleMixin>>` for subjecthood in identity semantics.
- no synthetic `IdentityBearingEntity` or `MachineIdentity` kind in Core;
- rigid identity providers come from profiles/domain ontologies (e.g., Person, Organization, Device, Workload, SoftwareAgent).

Reason: heterogeneous entities have different identity principles but may contextually play the same identity roles.

## O05 — DigitalIdentity / Identifier / IdentityContext — COMPLETE
- `DigitalIdentity` retained as a managed representation information artifact.
- `Identifier` retained as a scoped information/sign artifact; DID/SPIFFE ID are mappings/specializations.
- `IdentityContext` modeled as a contextual situation and explicitly distinguished from AdministrativeDomain, TrustDomain, AuthorizationContext, Audience and social context.
- Account/Profile remain P01 and may specialize/relate to DigitalIdentity without redefining it.

## O06 — Claim / Credential / Evidence / Proof — COMPLETE
- Claim = proposition/assertion information object.
- IdentityAttribute = identity-information element, not automatically an intrinsic quality.
- Credential = issued information artifact with claims/provenance/status.
- Evidence = `<<roleMixin>>` that heterogeneous artifacts can play.
- Proof = specialized evidential `<<roleMixin>>`; cryptographic proof types remain profile-level.
- a Credential may play Evidence/Proof roles without becoming the same concept.

## O07 — Proofing / Enrollment / Binding — COMPLETE
- IdentityProofing = evidence-evaluation event/process establishing identity confidence.
- Enrollment = event/process establishing managed representation/relationship.
- IdentityBinding = `<<relator>>` mediating subject and DigitalIdentity/Credential/Authenticator, grounded by Evidence.
- Provisioning remains P01 and is not a subtype/synonym of Enrollment.

## O08 — Authentication / Authenticator / Result / Assurance — COMPLETE
- Authentication = event/process.
- Authenticator = heterogeneous `<<roleMixin>>`.
- AuthenticationResult = result information artifact, distinct from Session.
- AssuranceAssessment = dimension-specific assessment artifact; proofing/authentication/federation/attribute assurance must not share one unqualified scale.
- Session remains P01.

## O09 — Authorization kernel — COMPLETE
Core minimum:
- Principal (`<<roleMixin>>`)
- Resource (`<<roleMixin>>`)
- Action (action-specification information object)
- AuthorizationRequest
- AuthorizationContext (`<<situation>>`)
- Authorization (`<<event>>`)
- AuthorizationResult
- Permission (normative information object)
- AccessGrant (`<<relator>>`)
- Delegation (`<<relator>>`)

Excluded from Core: full policy languages, PDP/PEP architecture, IAM role bundles, entitlement catalogs and platform-specific conditions.

## O10 — Trust alignment — COMPLETE
- TrustAssessment = assessment artifact/hook.
- TrustReference = explicit external alignment/reference artifact only.
- ONTrust:Trust remains an external alignment target; CM4DI does not redefine it.
- TrustFramework, TrustRegistry/TrustedList, TrustAnchor/Chain/Domain and certification/accreditation are P04/P03 profile constructs.

## O11 — Lifecycle model — COMPLETE
Decision: use **separate lifecycle families** rather than one catch-all identity lifecycle hierarchy.

### Core
- CredentialStatus mode
- CredentialLifecycleEvent
- CredentialIssuance
- Enrollment can create a DigitalIdentity/IdentityBinding.
- DigitalIdentity may carry lifecycle status in formal/data layers, but no universal `IdentityLifecycleEvent` class is introduced at Gate C because account/session/governance lifecycle evidence has different identity criteria and transition semantics.

### P01
Account lifecycle and Session lifecycle.

### P02
Presentation/exchange and VC-specific status/revocation mechanisms.

### P03
Credential rotation, workload/device registration/attestation and agent identity lifecycle.

### P04
Certification/accreditation/ecosystem participation lifecycle and government/legal status.

This preserves cross-lifecycle distinctions required by Gate B.

## O12 — Consent/privacy boundary — COMPLETE
- No full Consent/Privacy ontology enters Core.
- CM4DI may represent that disclosure/use was authorized when required by a CQ/profile.
- purpose, lawful basis, retention, consent receipts, privacy preference/policy and data-protection obligations remain external mappings/profile concerns.
- SelectiveDisclosure remains P02.

## O13 — Workload / Device / Agent compatibility — COMPLETE
- Core is non-human compatible through role patterns, not a machine-specific superclass.
- P03 supplies Workload, Device and SoftwareAgent/AI Agent domain kinds.
- Workload ≠ ServiceAccount ≠ ServicePrincipal ≠ WorkloadIdentity.
- Device ≠ DeviceIdentityRecord ≠ DeviceCredential ≠ Authenticator.
- AI Agent delegated access reuses Core Delegation; autonomous access reuses AccessGrant.
- attestation reuses Core Evidence/IdentityBinding/Assurance semantics.

## Inputs from other repositories
- OGCM-RF: used for governance, stable IDs, CQ/concept metadata and freeze discipline.
- conceptualization-ontology: used only as an example of layered model organization/freeze workflow.
- These repositories are not cited as empirical or scholarly evidence for digital-identity semantics.
- No accessible `cm4si` repository was found under the connected GitHub account during this Wave; therefore no unverified dependency on it was introduced.

## Exit to O14–O16
All O01–O13 decisions are now represented in governed artifacts. Final Gate-C readiness depends on UFO/OntoUML stereotype correction, anti-pattern pass, cardinality/interface check and frozen-model QC.