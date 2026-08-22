# CM4DI Journal V2 — Gate B Decision Package

**Gate:** B — Evidence and Scope Lock  
**Status:** READY FOR USER DECISION — no OntoUML/OWL refactor has been executed.  
**Evidence base:** 134 curated evidence items across seven completed discovery streams.

## 1. Recommended research mission
Retain the approved mission with a sharpened formulation:

> **CM4DI is a UFO-grounded, modular reference ontology for semantic interoperability across heterogeneous digital-identity paradigms, standards, trust frameworks and operational IAM ecosystems.**

The ontology is not an SSI ontology, IAM product metamodel, government-ID ontology, social-identity ontology or cybersecurity ontology. These ecosystems are represented through mappings and governed profiles around a protocol/vendor-neutral Core.

## 2. Recommended architecture
Approve a **Minimal Semantic Core + Four Profiles** architecture.

### Core
The Core should contain only concepts/patterns required to explain identity-bearing entities, digital identity representations, identifiers, identity information/evidence, authentication, minimal authorization, lifecycle, provenance/binding, assurance and trust alignment across multiple paradigms.

### Profile P01 — Enterprise / Federation
Account, Profile, IdentitySource, Directory, AdministrativeDomain, Application/Client, Federation, Broker/Intermediary, Provisioning, AttributeMapping, Group/Membership, Session, PermissionBundle, AccessPolicy/Condition, Social Login mapping.

### Profile P02 — Wallet / Verifiable Credentials
Issuer, Holder, CredentialPresentation, Wallet/HolderService, Controller, VerificationMethod, DataRegistry mappings, SelectiveDisclosure, VC/DID/OpenID4VC/EUDI mappings.

### Profile P03 — Machine / Workload / Device / Agent
Workload, ServiceAccount/WorkloadIdentity, Device/DeviceIdentityRecord, Attestation, TrustDomain/TrustBundle, temporary credentials/token exchange, AI Agent/AgentIdentity and delegated/autonomous agent access.

### Profile P04 — Trust / Assurance / Government
TrustFramework/GovernanceFramework, TrustRegistry/TrustedList, TrustAnchor/Chain, GovernanceAuthority/Registrar/Regulator/CAB, certification/accreditation/ecosystem participation, LegalIdentity/PID/government attestations.

## 3. Core decisions recommended
The normalized Gate-B register contains 75 decision families: **32 Core, 36 Profile, 3 Deferred, 3 Reject, 1 Social-Future**. `Core` here means retain/refine/admit as a Core semantic pattern; it does not mean 32 brand-new classes.

### Existing Core concepts to retain/refine
- Party / IdentitySubject — foundational/role redesign for human and non-human bearers.
- DigitalIdentity — retain as protocol-neutral digital representation.
- IdentityContext — retain but narrow; do not overload with authorization/admin/trust/social contexts.
- Identifier — retain; DID/SPIFFE ID/Pseudonym are profile specializations.
- IdentityAttribute — retain with provenance/binding semantics.
- Claim — retain with ontology-level definition distinct from token syntax.
- Credential — retain generic with explicit profile categories/lifecycles.
- Authenticator, Authentication, AuthenticationResult — retain with stricter separation from device, proofing and session.
- Authorization/AuthorizationResult — retain and expand a minimal semantic kernel.
- RelyingParty/Verifier — remodel as contextual roles.
- TrustReference and ONTrust:Trust — retain as alignment/trust hooks, not governance catch-alls.
- Enrollment — retain but explicitly separate from proofing, provisioning and ecosystem registration.

### New/strengthened Core semantic patterns recommended
1. Identity-Bearing Entity / IdentitySubject foundational pattern.
2. Identity Evidence.
3. Identity Proofing.
4. Evidence / Proof pattern.
5. Attribute Provenance.
6. Attribute / Identity Binding.
7. Credential Status and typed Credential Lifecycle.
8. Resource.
9. Action.
10. Authorization Request.
11. Authorization Context.
12. Principal.
13. Permission.
14. Access Grant / Assignment.
15. Delegation / `actsOnBehalfOf`.
16. Assurance Assessment with dimension/level.
17. Systematic Role-in-Interaction modeling pattern.

These are the major semantic gaps that the conference baseline cannot represent cleanly.

## 4. Existing concepts recommended for repositioning
### `Subscriber`
Move out of the minimal universal Core candidate and retain as NIST/profile mapping unless a generic subscription relation is independently required.

### `CredentialServiceProvider`
Do not use as the universal issuer/provider abstraction. Introduce a neutral contextual **Issuer** role in profiles and preserve CSP as a NIST-compatible mapping.

### `IdentityProvider`
Narrow its semantics to an authentication/federation provider role. Do not use it as synonym for IdentitySource, broader IdentityServiceProvider or AttributeProvider.

### `Verifier`
Resolve semantic overload by distinguishing authentication verification from credential-presentation verification.

## 5. Explicit non-admissions to Core
The following are intentionally **not** promoted to Core despite being important:
- Account, Profile, Directory, Session, Provisioning;
- Federation, Assertion, Broker;
- Wallet, Holder, Controller, SelectiveDisclosure;
- TrustFramework, Registry, TrustedList, TrustAnchor, GovernanceAuthority;
- LegalIdentity and government PID;
- Workload, ServiceAccount, Device, AI Agent;
- full Policy/Obligation language;
- full consent/privacy ontology;
- social/group/role identity, persona and reputation;
- vendor constructs and identity-pool terminology;
- Paradigm/Ecosystem and Interoperability as domain ontology classes.

## 6. Social-identity scope decision
Approve **Social-Future** as a formal disposition. Social Identity in the psychosocial/sociological sense is excluded from CM4DI Core and profiles except bridge/reference mappings. Social Login remains an Enterprise/Federation authentication mechanism. The evidence supports a future independent UFO-grounded Social Identity Ontology research track, but it is not part of this journal scope.

## 7. Semantic constraints that Wave 5 must preserve
- IdentitySubject ≠ Person.
- DigitalIdentity ≠ Account/Profile ≠ LegalIdentity.
- Principal ≠ IdentitySubject.
- IAM Role ≠ UFO Role.
- Claim ≠ Evidence ≠ Proof ≠ Credential.
- Authentication ≠ IdentityProofing ≠ Authorization.
- AuthenticationResult ≠ Session.
- AuthorizationDecision ≠ AccessGrant.
- IdentityContext ≠ AuthorizationContext ≠ AdministrativeDomain ≠ TrustDomain.
- Trust relation ≠ TrustFramework ≠ TrustRegistry ≠ TrustAnchor.
- Device ≠ DeviceIdentityRecord ≠ DeviceCredential ≠ Authenticator.
- Workload ≠ WorkloadIdentity ≠ ServiceAccount ≠ Principal.
- SocialLogin ≠ SocialIdentity.
- Lifecycle state labels must be typed by target domain (credential/account/session/participation).

## 8. Methodology lock recommendation
Proceed with the journal method as:

**Design Science Research → Bounded Structured Multi-Source Evidence Synthesis → Ontology Requirements & Competency Questions → UFO/OntoUML Conceptual Analysis → Modular Ontology Engineering → Standard/System Profile Mapping → OWL/SHACL Operationalization → Multi-Ecosystem Evaluation.**

The bounded evidence review is considered sufficient for scope lock because new sources in the final discovery waves largely reinforced existing distinctions rather than producing new Core-level families. A new exhaustive SLR is not required for this journal extension.

## 9. Evaluation design implications
Gate B does not execute evaluation, but it fixes the evidence portfolio that later Gate D should operationalize:
- W3C VC/DID and OpenID conformance suites for executable standard semantics;
- EUDI Wallet for wallet/government scenario;
- Keycloak for enterprise/federation scenario;
- SPIRE for workload identity scenario;
- MOSIP for foundational/government identity scenario;
- LANL and RBA datasets for authentication-event/context instantiation;
- World Bank ID4D 2025 as government/digital-ID context dataset;
- competitor comparison led by MFSSIA, Comb & Martin, Richter & Anke, Yildiz et al., and the enterprise IAM metamodel literature.

## 10. Novelty lock recommendation
Do **not** claim first digital-identity ontology, first UFO-grounded identity ontology, first interoperable identity model, or universal identity ontology.

Defensible contribution hypothesis:

> Existing work provides broad surveys and ontological fragments, SSI-specific conceptual/reference models, enterprise IAM metamodels, and a recent UFO-grounded ontology for a specialized SSI authentication setting. CM4DI addresses a different gap: a foundationally grounded, modular reference ontology designed to align heterogeneous identity paradigms, standards, trust frameworks and operational IAM ecosystems through explicit semantic mappings and reproducible multi-layer evaluation.

## 11. Gate-B acceptance criteria
Gate B should be approved only if the following are accepted as the design boundary:
- minimal Core + four profiles;
- human and non-human identity subjects supported without one `MachineIdentity` catch-all;
- the 17 new/strengthened Core semantic patterns above enter Wave-5 conceptual analysis;
- profile-specific constructs are not promoted to Core without new contradictory evidence;
- social identity remains separate;
- canonical ontology/model remain unchanged until Wave 5 starts after approval.

## 12. Next step after approval
Execute **Wave 5 — Conceptual Model Revision (O01–O16)** in controlled domain clusters:
1. foundational bearer/subject/representation/context;
2. claim/evidence/proof/credential/binding/lifecycle;
3. authentication/assurance/session boundary;
4. minimal authorization kernel and delegation;
5. trust alignment and profile boundary;
6. non-human compatibility;
7. role stereotypes and OntoUML anti-pattern pass;
8. competency-question traceability and Core freeze.

Wave 5 must end at **Gate C — Conceptual Model Freeze** before any major OWL refactor.
