# EUDI Change Impact — 2026-08-29

## Current-version finding
The EUDI Wallet Architecture and Reference Framework **v3.0.0** is the latest published release as of this review. The official GitHub release identifies the v3 changes as alignment with the July 2026 amending Implementing Regulations, introduction of Relying Party Services, trust-anchor retrieval through Trusted Lists and Lists of Trusted Entities, wallet-to-wallet changes and introduction of the Functional Conformance Assessment Framework (FCAF).

The legal baseline must therefore distinguish original implementing acts from their current/amending lineage. EUR-Lex currently exposes consolidated 11 August 2026 versions for material acts including CIR 2024/2977 and 2024/2982.

## Semantic impacts assessed

### 1. Relying Party registration is a governance lifecycle, not merely federation metadata
CIR 2025/848 defines national registers, registrars, registration data, intended use, wallet-relying-party access certificates, optional registration certificates, suspension/cancellation and record keeping. This strengthens existing CM4DI `TrustRegistry`, `Registrar`, `EcosystemParticipation`, `ParticipantStatus`, `RelyingParty`, `AccessPolicy` and credential/evidence mappings.

**Decision:** no new Core concept required. EUDI-specialized constructs stay profile/mapping level.

### 2. Relying Party Service may need a profile mapping, not a new Core class
ARF v3 introduces Relying Party Services. The distinction is useful because a legal/organizational relying party may expose multiple services/use surfaces.

**Decision:** map initially to Application/Resource/service realization. Do not add a Core or profile class until detailed ARF extraction demonstrates stable cross-ecosystem value.

### 3. Trust sources are more differentiated
ARF v3 requires Wallets, Relying Parties and issuers to retrieve/manage trust anchors from Trusted Lists and Lists of Trusted Entities. This reinforces:

`TrustFramework != TrustRegistry != TrustedList != TrustAnchor != TrustAssessment`.

**Decision:** current Trust Governance decomposition is strengthened; no merge justified.

### 4. FCAF is evaluation infrastructure, not an ontology primitive
ARF v3 Section 7.5 introduces reusable functional conformance test cases and explicitly positions functional conformance as complementary to security evaluation/certification.

**Decision:** use FCAF in Gate-D/Wave-8 conformance evaluation; do not model FCAF as a Core semantic concept.

### 5. Wallet Unit and Wallet Solution are operational compositions
CIR 2024/2977/2979 distinguish wallet solution, wallet unit and wallet instance. These are valuable EUDI architecture constructs but are more implementation-specific than the neutral CM4DI `Wallet` role.

**Decision:** preserve EUDI mapping specialization; do not replace the CM4DI Wallet concept or create a universal Core hierarchy.

### 6. Wallet Unit Attestation is distinct from PID/EAA and user authentication
CIR 2024/2979 and 2024/2982 use Wallet Unit Attestations for wallet authenticity/validity, while PID/EAA carry identity/attribute information and wallet-user authentication gates access/use.

**Decision:** map Wallet Unit Attestation through Evidence/Proof/Credential-profile semantics; retain `Authentication != CredentialPresentation != Attestation`.

### 7. Intended use introduces policy/purpose semantics but does not justify a generic purpose ontology in Core
CIR 2025/848 binds relying-party registration to intended use and allowed requested attributes, including a general access policy.

**Decision:** relate to `AccessPolicy`, `AccessCondition`, `PresentationRequest`, ODRL/DPV mappings and Trust Governance. Avoid importing complete privacy/purpose semantics into CM4DI Core.

### 8. Registration lifecycle reinforces temporal governance modeling
Suspension/cancellation of relying-party registration and associated certificate revocation strongly support explicit `EcosystemParticipation` and `ParticipantStatus` lifecycle semantics.

**Decision:** retain current Trust Governance Domain and ensure formalization supports participation/status relationships without overloading CredentialStatus.

## DDD impact
No EUDI v3/legal evidence currently justifies renaming, merging or splitting the 15 canonical CM4DI Domains or 13 Bounded Contexts. In particular:

- Credential Exchange remains distinct from Credential Management.
- Trust Governance remains distinct from Government Identity.
- Federation remains distinct from Identity Administration.
- Authentication remains distinct from Identity Evidence/Credential Presentation.

All canonical Domain and Bounded Context names continue to satisfy the no-`and`, no-`&`, no-slash-composed semantic-center rule.

## Module-architecture impact
No immediate change to Draft PR #59 is required from the EUDI evidence extracted so far. However:

- Trust Governance ↔ Credential Exchange dependencies need explicit mappings for trusted lists/anchors and RP registration certificates.
- Government Identity ↔ Credential Lifecycle mappings must explicitly represent PID/EAA specialization.
- EUDI profile artifacts should be external mappings/instances rather than owned definitions in aggregate profile entrypoints.

Final verdict remains blocked on complete #62 extraction and #66 regression.

## Evaluation impact
Gate D should include at least one EUDI end-to-end scenario covering:
1. registered Wallet-Relying Party;
2. intended use/attribute request;
3. RP authentication/registration certificate validation;
4. wallet-user authentication/approval;
5. selective disclosure/presentation;
6. trust-anchor/list resolution;
7. verification and status handling;
8. governance lifecycle or conformance evidence.

FCAF/reference implementation should be used where feasible as executable conformance evidence, separately from ontology reasoning/CQ evaluation.

## Sources used in this pass
- Regulation (EU) 2024/1183.
- CIR 2024/2977 current/consolidated lineage.
- CIR 2024/2979.
- CIR 2024/2980.
- CIR 2024/2981.
- CIR 2024/2982 current/consolidated lineage.
- CIR 2025/848 and 2026 amendment lineage.
- EUDI ARF v3.0.0 official release/changelog and official EUDI documentation landing page.

Exact source locators/coverage remain governed in `EUDI_SOURCE_COVERAGE.csv` and the Source Completeness registries.