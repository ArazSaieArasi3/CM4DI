# CM4DI Journal V2 — Gate C Decision Package

**Gate:** C — Conceptual Model Freeze  
**Status:** READY FOR USER APPROVAL  
**Date:** 2026-08-22

## Decision requested
Approve the Wave-5 conceptual semantics as the authoritative journal-v2 design basis for Profile construction and later formal OWL/SHACL implementation.

## Proposed Core architecture
The frozen candidate contains 34 concepts/role/relator/event patterns and 55 governed relations organized into eight semantic clusters:
1. Subjecthood and interaction roles
2. Digital representation and context
3. Identity information / claims / evidence / binding
4. Credential semantics and lifecycle
5. Identity proofing and enrollment
6. Authentication and assurance
7. Minimal authorization kernel
8. Trust/assurance alignment hooks

## Key model decisions requiring approval

### 1. Party and IdentitySubject are contextual roleMixins
They are not universal rigid entity kinds. Person, Organization, Device, Workload and SoftwareAgent/AI Agent retain their own identity principles in domain/profile models and may play these Core roles.

### 2. DigitalIdentity is a representation artifact
DigitalIdentity represents an IdentitySubject in IdentityContext. Account/Profile are P01 representations; LegalIdentity is P04; none is automatically identical to the subject.

### 3. Evidence and Proof are roleMixins
This was the main UFO correction in Wave 5. A Credential, document, assertion, record or attestation artifact can play Evidence/Proof roles. Evidence/Proof therefore do not impose one artifact identity principle.

### 4. IdentityBinding is a relator
Subject↔DigitalIdentity/Credential/Authenticator binding is not a bare association. The relator may be grounded by evidence and established through enrollment/proofing/attestation patterns.

### 5. Proofing, Enrollment and Authentication are distinct events
- IdentityProofing establishes identity confidence from evidence.
- Enrollment establishes managed identity representation/relationship.
- Authentication verifies an actor/subject/authenticator in context.
- Provisioning remains P01.

### 6. Authorization receives a minimal Core kernel
Principal, Resource, Action, AuthorizationRequest, AuthorizationContext, Permission, AccessGrant, Delegation and explicit AuthorizationResult semantics enter Core because the same pattern recurs across standards, enterprise IAM and machine/agent scenarios.

`AccessGrant` and `Delegation` are relators. Full policy-language semantics remain profile-level.

### 7. Trust is decomposed
Core contains TrustAssessment and TrustReference/alignment hooks. TrustFramework, Registry/TrustedList, TrustAnchor/TrustChain/TrustDomain and certification/accreditation remain P04/P03 and are not synonyms of trust relation/assessment.

### 8. Four profiles remain mandatory
- P01 Enterprise / Federation
- P02 Wallet / Verifiable Credentials
- P03 Machine / Workload / Device / Agent
- P04 Trust / Assurance / Government

### 9. No MachineIdentity superclass
Workload, Device and AI Agent are different kinds/contexts. They reuse IdentitySubject, DigitalIdentity, Identifier, Credential, Evidence, Principal, AccessGrant and Delegation through P03.

### 10. Social Identity stays outside CM4DI
SocialLogin is a P01 federation/authentication mapping. SocialIdentity, Persona, Reputation, Salience, GroupIdentity and related psychosocial constructs remain future/external.

## Explicit removals/reclassifications from conference Core treatment
- IdentityProvider → profile-first contextual provider/federation role
- CredentialServiceProvider → profile/mapping; neutral issuer roles in P02/P04
- Subscriber → profile/NIST mapping
- RelyingParty → retained but reclassified as roleMixin
- Verifier → retained only as generic role pattern with profile specializations
- TrustReference → retained but narrowed to alignment/reference function

## Lifecycle decision
CM4DI does not introduce one catch-all lifecycle hierarchy. Credential lifecycle is explicit in Core. DigitalIdentity creation/binding is covered through Enrollment; Account, Session, Participation/Certification and machine-specific lifecycles remain in their profiles.

## Privacy decision
No full consent/privacy ontology enters Core. Minimal authorization of disclosure may be linked where CQs require it; detailed privacy semantics use external/profile mappings.

## Governed requirements
32 competency questions are frozen as the requirements baseline for formalization/evaluation. `CM4DI-CQ0032` is the cross-paradigm sufficiency test: the same Core must support federated employee login, VC presentation, SPIFFE workload identity and government digital-ID scenarios without introducing vendor/protocol classes into Core.

## Quality result
Wave-5 QC: **PASS**, estimated bounded quality ~4.9/5 (~97%).

The anti-pattern pass contains 40 explicit checks. The only major correction found during the pass—Evidence/Proof stereotype classification—has already been applied.

## Baseline preservation
Published conference artifacts remain unchanged:
- `CM4DI.owl`: `e04ae62319aac1c123877b0b03acf3f5137a9849`
- `CM4DI-Generation2-Version15.drawio`: `0dce512f4c0611ccaf2fd5665d6148fb379b22af`

## Freeze artifacts
Canonical Gate-C semantic sources:
- `model/journal-v2/CM4DI_CORE_CONCEPT_REGISTRY_v2.csv`
- `model/journal-v2/CM4DI_CORE_RELATION_REGISTRY_GATE_C.csv`
- `model/journal-v2/CORE_PROFILE_BOUNDARY_v2.md`
- `research/COMPETENCY_QUESTION_REGISTRY_v2.csv`

Derived structural view:
- `model/journal-v2/CM4DI_CORE_CONCEPTUAL_MODEL_v2.mmd`

Manifest:
- `model/journal-v2/GATE_C_FREEZE_MANIFEST.yaml`

## What approval enables
After Gate C approval:
1. Wave 6 may design the four profiles and explicit mappings around the frozen Core.
2. Wave 7 may refactor the formal ontology, add SHACL, deterministic serializations, CI/reasoner checks and executable SPARQL CQs.
3. Any later Core semantic change requires a change record and impact analysis against CQs, mappings, profiles and evaluation.

## Gate decision
**Recommended decision: APPROVE Gate C.**

No Wave 6 or formal OWL refactor should begin until this approval is explicit.