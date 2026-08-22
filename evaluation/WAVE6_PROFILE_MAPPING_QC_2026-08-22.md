# CM4DI Journal V2 — Wave 6 Profile & Mapping QC

**Date:** 2026-08-22  
**Scope:** P01–P04 design, cross-profile integration, governed mappings, profile-specific CQs.

## Overall result
**PASS — Wave 6 profile architecture and mapping baseline are ready for formalization in Wave 7.**

This PASS does not mean OWL/SHACL profile modules have already been generated. It means the profile semantics, boundaries, mappings and competency requirements are sufficiently governed to serve as formalization inputs.

## Quantitative summary
- Gate-C Core concepts/patterns reused: 34.
- Core CQs retained: 32.
- Profile concepts: **68** (P01=20, P02=12, P03=18, P04=18).
- Profile relations: **64** (P01=19, P02=13, P03=16, P04=16).
- Governed external/profile mapping assertions: **68**.
- New profile CQs: **20**; total governed CQs now **52**.
- Cross-profile scenario checks: **6/6 PASS**.
- Four profile interface contracts preserved: **4/4 PASS**.

## Mapping quality rules checked
1. Every mapping has a stable `CM4DI-MAP` identifier — PASS.
2. Every mapping specifies subject, predicate, object, external family and status — PASS.
3. Exact equivalence is used conservatively — PASS.
4. Vendor-specific constructs use `implementation` unless semantics justify stronger correspondence — PASS.
5. Broader/narrower/related mappings are distinguished from implementation mappings — PASS.
6. No vendor term is promoted to Core because of popularity or implementation convenience — PASS.
7. IAM Role/PermissionSet never maps to UFO Role — PASS.
8. DID maps to Identifier, not DigitalIdentity — PASS.
9. SPIFFE ID maps to Identifier and SVID to Credential — PASS.
10. Framework assurance levels map to AssuranceAssessment dimensions, not one global LoA — PASS.

## Profile semantic checks
### P01
- Account != IdentitySubject — PASS.
- Session != AuthenticationResult — PASS.
- Provisioning != Enrollment — PASS.
- AdministrativeDomain != IdentityContext — PASS.
- Application != ApplicationRegistration — PASS.
- Federation != FederationConnection — PASS.

### P02
- Holder != Credential subject — PASS.
- Controller != Holder — PASS.
- CredentialPresentation != Authentication — PASS.
- VerifiablePresentation != Credential — PASS.
- SelectiveDisclosure != Consent — PASS.

### P03
- No MachineIdentity superclass — PASS.
- Workload != ServiceAccount/ServicePrincipal — PASS.
- Device != DeviceIdentityRecord/Authenticator — PASS.
- SPIFFE ID != SVID — PASS.
- Attestation != Authentication/Proofing — PASS.
- AgentIdentity != AIAgent — PASS.
- Delegated vs autonomous agent access separated — PASS.

### P04
- TrustAssessment != TrustFramework — PASS.
- TrustRegistry/TrustedList != TrustAnchor/TrustChain — PASS.
- Certification != Accreditation — PASS.
- EcosystemParticipation != Enrollment — PASS.
- ParticipantStatus != CredentialStatus — PASS.
- LegalIdentity != DigitalIdentity — PASS.
- PID != IdentityAttribute — PASS.
- Cryptographic validation != institutional conformance — PASS.

## Cross-profile regression checks
- EUDI split between P02 interaction and P04 governance/legal semantics without duplication — PASS.
- Workload federation split between P01 federation and P03 bearer/representation semantics — PASS.
- Agent enterprise access reuses Core Delegation/AccessGrant and P01 application/session semantics — PASS.
- SPIFFE TrustDomain remains distinct from P04 TrustFramework — PASS.
- SocialIdentity remains outside all four profiles; SocialLogin is P01 mapping only — PASS.

## CQ readiness
All 20 profile CQs reference profile and Core concepts explicitly. They cover account/source/federation/session/permissions; issuer/holder/presentation/proof; workload/attestation/device/agent; and framework/certification/assurance/legal-identity distinctions. They are ready to be converted into executable SPARQL tests in Wave 7/8.

## QC dimensions
| Dimension | Score | Note |
|---|---:|---|
| Core/Profile boundary preservation | 5.0/5 | No profile convenience changed frozen Core semantics. |
| Profile semantic coverage | 4.9/5 | Four intended ecosystems represented at bounded journal scope. |
| Mapping discipline | 5.0/5 | Exact/implementation/related/narrower semantics distinguished. |
| Ontological anti-conflation | 5.0/5 | High-risk lexical collisions explicitly controlled. |
| Cross-profile integration | 4.9/5 | Six representative combined scenarios pass. |
| CQ traceability | 4.9/5 | 20 profile CQs complement 32 Core CQs. |
| Formalization readiness | 4.8/5 | Conceptual inputs ready; OWL/SHACL constraints remain Wave 7 work. |
| Reproducibility readiness | 4.9/5 | Stable IDs and governed registries available. |

**Estimated bounded execution quality: ~4.9/5 (~98%).**

## Residual risks for Wave 7
- Decide precise OWL expression for roleMixins/relators without weakening UFO semantics.
- Choose module import graph and canonical source representation.
- Convert conceptual cardinalities to OWL/SHACL carefully; not every conceptual constraint belongs in OWL DL.
- Define formal mappings without overusing `owl:equivalentClass`/`owl:equivalentProperty`.
- Preserve profile independence while allowing explicit P01↔P03 and P02↔P04 reuse.
- Generate deterministic serializations and reasoner/SHACL/SPARQL regression tests.

## Wave 6 verdict
**PASS. Proceed to Wave 7 — formal ontology and automation.**