# CM4DI Journal V2 — Core/Profile Boundary Candidate

**Wave:** 5 — Conceptual Model Revision  
**Status:** Gate-C candidate, not yet formal-ontology release  
**Input:** Approved Gate B synthesis

## Architectural rule
The Core contains only semantics that recur across multiple digital-identity paradigms and are required by stable competency questions. Paradigm-, protocol-, jurisdiction- and vendor-specific concepts remain in profiles or mappings.

## Core semantic clusters

### C1 — Subjecthood and interaction
- `IdentitySubject` — anti-rigid heterogeneous contextual role (`<<roleMixin>>` candidate).
- `Party` — anti-rigid participant role (`<<roleMixin>>` candidate), not a universal entity kind.
- `RelyingParty` — contextual interaction role; specializes/depends on Party participation.
- `Verifier` — generic verification role pattern only; concrete verifier semantics specialize in profiles.
- `Principal` — contextual authorization role; may be played by human/non-human entities or managed representations.

**Boundary:** Person, Organization, Device, Workload and SoftwareAgent are not forced into one artificial Core kind. Their domain kinds come from profiles or external domain models and may play Core roles.

### C2 — Digital representation and context
- `DigitalIdentity`
- `Identifier`
- `IdentityContext`

**Boundary:** `Account`, `UserProfile`, `AdministrativeDomain`, `TrustDomain`, `Wallet`, `DeviceIdentityRecord` and `AgentIdentity` are profile specializations/related artifacts, not Core aliases.

### C3 — Identity information, assertion and evidence
- `IdentityAttribute`
- `Claim`
- `Evidence`
- `Proof` as an evidence-use role/pattern rather than an all-purpose cryptographic class
- provenance/source relations
- `IdentityBinding` relational/relator pattern

**Boundary:** social self-description, Persona and Reputation remain outside CM4DI; technical attribute mapping stays P01; cryptographic proof types stay P02/P03.

### C4 — Credential semantics and lifecycle
- `Credential`
- `CredentialStatus`
- `CredentialIssuance`
- abstract `CredentialLifecycleEvent`

**Boundary:** VC Presentation, DID Controller, SVID, device certificates and temporary cloud tokens specialize/map through profiles.

### C5 — Proofing and enrollment
- `IdentityProofing`
- `Enrollment`
- `IdentityBinding`
- evidence and assurance links

**Boundary:** Provisioning is P01; device join/attestation is P03; legal proofing schemes are P04.

### C6 — Authentication and assurance
- `Authentication`
- `Authenticator` as heterogeneous contextual role
- `AuthenticationResult`
- `AssuranceAssessment`

**Boundary:** Session and social login/federation transactions are P01; WebAuthn/attestation mechanics are profile mappings.

### C7 — Minimal authorization kernel
- `Authorization`
- `AuthorizationRequest`
- `AuthorizationContext`
- `AuthorizationResult`
- `Principal`
- `Resource` as contextual access target role
- `Action` as requested action type/intention
- `Permission`
- `AccessGrant`
- `Delegation`

**Boundary:** full policy languages, IAM role bundles, conditions, enforcement-point architecture and entitlement catalogs are profile/mapping concerns.

### C8 — Trust and assurance hook
- `TrustAssessment`
- `TrustReference` as an alignment/reference artifact, no longer a catch-all trust concept
- `AssuranceAssessment`
- explicit alignment to external `ONTrust:Trust`

**Boundary:** `TrustFramework`, `TrustRegistry/TrustedList`, `TrustAnchor`, `TrustChain`, `TrustDomain`, accreditation/certification/participation are P04 (with TrustDomain shared with P03).

## Profile P01 — Enterprise / Federation
- Account
- UserProfile
- IdentitySource / AuthoritativeIdentitySource
- IdentityStore / Directory
- IdentityLink / ExternalIdentityReference
- AdministrativeDomain / Tenant / Realm
- Application / Client / ApplicationRegistration
- Federation / FederationConnection
- IdentityBroker / IdentityIntermediary
- Provisioning / SCIM / JIT / ProvisioningRule
- AttributeMapping
- Group / access-group membership
- Session
- TemporaryCredential where used operationally
- PermissionBundle / IAM Role
- AccessPolicy / Condition
- SocialLogin mapping

## Profile P02 — Wallet / Verifiable Credentials
- Issuer role
- Holder role
- CredentialPresentationVerifier
- CredentialPresentation / VerifiablePresentation
- Wallet / HolderService / WalletProvider
- Controller
- VerificationMethod
- VerifiableDataRegistry
- SelectiveDisclosure
- DID as Identifier specialization/mapping
- VC / mdoc / government attestation as Credential specializations

## Profile P03 — Machine / Workload / Device / Agent
- Workload / RuntimeInstance
- WorkloadIdentity
- ServiceAccount
- ServicePrincipal mapping
- ManagedIdentity mapping
- FederatedWorkloadPrincipal
- Device
- DeviceIdentityRecord
- DeviceRegistration / Join
- DeviceCredential
- NodeAttestation / WorkloadAttestation
- SPIFFE ID mapping to Identifier
- SVID mapping/specialization of Credential
- TrustDomain / TrustBundle
- AI Agent / AgentIdentity
- Sponsor / AccountableOwner
- AutonomousAccess and delegated-agent access mapped through AccessGrant/Delegation

**Explicit rejection:** no generic `MachineIdentity` superclass.

## Profile P04 — Trust / Assurance / Government
- TrustFramework / GovernanceFramework
- TrustRegistry / TrustedList
- TrustAnchor / TrustChain / technical trust infrastructure
- GovernanceAuthority / Regulator / Registrar / CAB
- Accreditation / Certification / EcosystemParticipation and their statuses
- LegalIdentity
- PersonIdentificationData
- GovernmentAttestation
- IdentityConfidenceProfile / framework-specific assurance scales
- Pseudonym specialization where legally/governance relevant
- institutional provider/participant roles

## Deferred / external boundaries
- Consent and privacy: only minimal `authorizedDisclosure`/sharing linkage if required by a CQ; no full consent or privacy ontology.
- Membership/Affiliation social semantics: external link/reference to W3C ORG/UFO where needed.
- Audit/transaction logs: evaluation/operational artifacts, not Core.
- Identity ecosystem/paradigm: research/mapping metadata, not ontology class.
- Interoperability requirement: CQ/evaluation metadata, not domain concept.
- SocialIdentity/Persona/Reputation/Salience: future independent ontology.

## Baseline classes requiring ontological reinterpretation

| Baseline concept | Gate-C candidate treatment |
|---|---|
| Party | Keep label but change from implicit general entity superclass to `<<roleMixin>>` participant pattern. |
| IdentitySubject | Keep; model as `<<roleMixin>>` played by heterogeneous domain entities. |
| DigitalIdentity | Keep and sharpen as managed information/representation artifact. |
| IdentityContext | Keep; narrow to interpretation/identity-management context. |
| IdentityAttribute | Keep; redefine as identity-information element rather than intrinsic quality by default. |
| Claim | Keep; ontology-level assertion, not token syntax member. |
| Credential | Keep; broad information artifact with claims/provenance/status. |
| Authenticator | Keep; model as heterogeneous contextual role. |
| Authentication | Keep event/process. |
| AuthenticationResult | Keep as explicit result/record, separate from Session. |
| Authorization | Keep but expand minimal kernel. |
| AuthorizationResult | Keep and redefine with explicit decision semantics. |
| IdentityProvider | Move toward profile contextual provider/federation role; do not treat as universal rigid Core actor. |
| CredentialServiceProvider | Move to profile/mapping; replace universal use with neutral Issuer/provider role patterns. |
| Verifier | Retain only generic verification role pattern; specialized verifier roles required. |
| RelyingParty | Retain as anti-rigid contextual role. |
| Subscriber | Move to NIST/Enterprise/Government profile mapping unless a Core CQ independently requires it. |
| Enrollment | Keep and separate from Proofing/Provisioning. |
| TrustReference | Keep only as explicit external-alignment/reference artifact. |
| ONTrust:Trust | Keep external foundational/domain alignment; no local redefinition. |

## Core admission test applied
A concept remains in Core only when it passes all of the following:
1. cross-paradigm recurrence;
2. required by one or more governed CQs;
3. stable semantics independent of vendor/protocol/jurisdiction;
4. compatible with UFO category analysis;
5. not reproducible more cleanly as a profile specialization or mapping;
6. its inclusion does not force human-, SSI-, enterprise- or government-centric assumptions.

## Gate-C freeze rule
The semantic boundary above is frozen only after the UFO/OntoUML stereotype review and anti-pattern pass. OWL/SHACL formalization must follow this model rather than redefine it.