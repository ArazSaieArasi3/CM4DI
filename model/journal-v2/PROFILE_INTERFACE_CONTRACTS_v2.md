# CM4DI Journal V2 — Profile Interface Contracts

## Purpose
Wave 5 freezes how profiles are allowed to specialize/map the Core. Detailed profile modeling happens in Wave 6; these contracts prevent profile concepts from silently changing Core semantics.

## P01 — Enterprise / Federation
### Required Core reuse
- Account/Profile MUST remain representations/records about an IdentitySubject and MUST NOT become the subject by default.
- Federation roles MUST map to `Party`, `RelyingParty`, `Verifier` and profile provider roles without retyping organizations/software as new Core kinds.
- Authentication MUST map to Core `Authentication`/`AuthenticationResult`; Session is an independent P01 construct.
- IAM Role/PermissionSet MUST map to P01 `PermissionBundle` and Core `Permission`/`AccessGrant`, never to UFO `Role` by lexical similarity.
- Provisioning MUST remain distinct from Core Enrollment and IdentityProofing.
- AttributeMapping/IdentitySource MUST connect to Core Claim/IdentityAttribute/Evidence provenance without redefining them.

### Minimum P01 scenario
Federated employee access: Person/employee-domain entity → IdentitySubject → Account → Federation → Authentication → Session; Principal → AccessGrant/Permission → Authorization.

## P02 — Wallet / Verifiable Credentials
### Required Core reuse
- Issuer/Holder/PresentationVerifier are contextual profile roles; Holder MUST NOT be assumed equal to Credential subject.
- VC/mdoc/government credential types specialize/map to Core Credential.
- DID maps to Identifier; controller/verification methods remain profile constructs.
- CredentialPresentation specializes a profile event/process and MUST NOT be collapsed into Authentication.
- SelectiveDisclosure is a presentation/privacy mechanism and does not create a new Core identity type.
- Cryptographic DataIntegrityProof/verification material may play Core Evidence/Proof roles.

### Minimum P02 scenario
Issuer issues Credential about IdentitySubject → Holder stores/controls credential → Holder presents selected credential/claims → CredentialPresentationVerifier evaluates Evidence/Proof and relies on Claims.

## P03 — Machine / Workload / Device / Agent
### Required Core reuse
- Workload/Device/SoftwareAgent are rigid/domain kinds supplied by P03 and may play IdentitySubject/Party/Principal roles.
- ServiceAccount/ServicePrincipal/ManagedIdentity MUST NOT be equated with Workload; they map to representation/account/principal patterns.
- SPIFFE ID maps to Identifier; SVID maps/specializes Credential and may play Evidence/Proof.
- Node/Workload Attestation uses Core Evidence/IdentityBinding/Assurance patterns.
- Device may independently play IdentitySubject and Authenticator; those role occurrences are not identical concepts.
- Agent delegated access MUST reuse Core Delegation; autonomous access MUST reuse AccessGrant.
- No `MachineIdentity` superclass is permitted.

### Minimum P03 scenarios
1. SPIFFE workload: Workload plays IdentitySubject + Principal; SPIFFE ID is Identifier; SVID is Credential; attestation grounds IdentityBinding.
2. Device: Device plays IdentitySubject and optionally Authenticator; DeviceIdentityRecord remains separate representation.
3. AI agent: SoftwareAgent plays IdentitySubject/Principal; sponsor/accountability is profile relation; delegated rights reuse Delegation.

## P04 — Trust / Assurance / Government
### Required Core reuse
- TrustFramework/Registry/TrustedList/TrustAnchor/TrustChain are not subtypes/synonyms of TrustAssessment.
- Framework-specific assurance levels specialize/map to `AssuranceAssessment` dimensions/values rather than replacing it.
- LegalIdentity/PID are profile constructs that may ground/relate to Core IdentitySubject/DigitalIdentity but do not redefine them.
- Accreditation, Certification and EcosystemParticipation have their own governance lifecycles and MUST NOT be modeled as Enrollment or CredentialStatus.
- TrustReference is only an alignment hook from Core to framework/external trust concepts.

### Minimum P04 scenario
Proofed person/legal identity basis → government DigitalIdentity/Credential → AssuranceAssessment → governed participant/provider status via TrustFramework/Registry/Certification, with trust assessments kept semantically separate.

## Privacy / consent boundary contract
CM4DI MAY represent that a disclosure/presentation/operation was authorized where a CQ needs it. It MUST NOT import a full consent, purpose, data-protection, retention or privacy-policy ontology into Core. P02/P04 may map to external consent/privacy vocabularies.

## External social-identity contract
- SocialLogin → P01 federation/authentication mapping.
- Affiliation/Membership may appear as Claim/IdentityAttribute values and link to external organization vocabularies.
- SocialIdentity, RoleIdentity, Persona, Reputation, Salience, SocialPerception and ContextCollapse remain outside all four CM4DI profiles except explicit bridge mappings.

## Profile conformance rule
A profile is conformant to the Gate-C Core only if:
1. it reuses the Core concept meaning without redefining its identity criterion;
2. it supplies rigid role players for abstract Core roleMixins when instantiated;
3. it declares every specialization/mapping explicitly;
4. it preserves all listed anti-conflation constraints;
5. it does not add a profile concept to Core through implementation convenience alone;
6. it can answer its profile-specific CQs using Core + profile semantics.