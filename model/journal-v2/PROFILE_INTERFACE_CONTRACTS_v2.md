# CM4DI Journal V2 — Profile Interface Contracts

## Status
Updated by DDD refactor #50. Profiles remain stable integration views P01–P04 but are explicitly **not Domains or Bounded Contexts**. Domain ownership is canonical in `ddd/DOMAIN_REGISTRY_v2.csv`; profile composition is canonical in `ddd/DOMAIN_PROFILE_MATRIX_v2.csv`.

## P01 — Enterprise Identity Profile
Legacy label: Enterprise / Federation.

### Required Domain reuse
- Account/Profile belong to Identity Administration and MUST remain representations/records about an IdentitySubject; they MUST NOT become the subject by default.
- Federation roles belong to Federation and map to `Party`, `RelyingParty`, `Verifier` and provider roles without retyping organizations/software as new Core kinds.
- Authentication MUST map to the Authentication subdomain; Session is an independent Authentication construct.
- IAM Role/PermissionSet MUST map into Authorization `PermissionBundle` and Core `Permission`/`AccessGrant`, never to UFO `Role` by lexical similarity.
- Provisioning belongs to Identity Administration and MUST remain distinct from Identity Establishment `Enrollment` and `IdentityProofing`.
- AttributeMapping/IdentitySource belong to Identity Administration and connect to Identity Information / Identity Evidence without redefining them.

### Minimum P01 scenario
Federated employee access composes Identity Representation → Identity Administration → Federation → Authentication → Authorization.

## P02 — Verifiable Credential Profile
Legacy label: Wallet / Verifiable Credentials.

### Required Domain reuse
- Issuer belongs primarily to Credential Management; Holder and CredentialPresentationVerifier belong to Credential Exchange.
- Holder MUST NOT be assumed equal to Credential subject.
- VC/mdoc/government credential types specialize/map to Credential Management `Credential`.
- DID maps to Identity Representation `Identifier`; controller/verification methods remain Credential Exchange constructs.
- CredentialPresentation belongs to Credential Exchange and MUST NOT be collapsed into Authentication.
- SelectiveDisclosure is a Credential Exchange capability and does not create a new Core identity type.
- Cryptographic DataIntegrityProof/verification material may play Identity Evidence `Evidence`/`Proof` roles.

### Minimum P02 scenario
Issuer issues Credential about IdentitySubject → Holder/Wallet manages credential → CredentialPresentation conveys selected claims/evidence → CredentialPresentationVerifier evaluates it.

## P03 — Technical Identity Profile
Legacy label: Machine / Workload / Device / Agent.

### Required Domain reuse
- Workload Identity, Device Identity and Agent Identity are separate subdomains with separate Bounded Contexts.
- Workload/Device/SoftwareAgent are rigid/domain kinds supplied by their subdomains and may play IdentitySubject/Party/Principal roles.
- ServiceAccount/ServicePrincipal/ManagedIdentity MUST NOT be equated with Workload; they are Workload Identity constructs linked to Identity Administration and Authorization.
- SPIFFE ID maps to Identifier; SVID maps/specializes Credential Management `Credential` and may play Identity Evidence roles.
- Node/Workload Attestation uses Identity Evidence/IdentityBinding.
- Device may independently play IdentitySubject and Authenticator; those role occurrences are not identical concepts.
- Agent delegated access MUST reuse Authorization `Delegation`; autonomous access MUST reuse `AccessGrant`.
- No `MachineIdentity` superclass is permitted.

### Minimum P03 scenarios
1. Workload: Workload plays IdentitySubject + Principal; SPIFFE ID is Identifier; SVID is Credential; attestation grounds IdentityBinding.
2. Device: Device plays IdentitySubject and optionally Authenticator; DeviceIdentityRecord remains separate representation.
3. Agent: SoftwareAgent/AIAgent plays IdentitySubject/Principal; AgentSponsor provides accountability; delegated rights reuse Delegation.

## P04 — Governed Identity Profile
Legacy label: Trust / Assurance / Government.

### Required Domain reuse
- TrustFramework/Registry/TrustedList/TrustAnchor/TrustChain belong to Trust Governance and are not subtypes/synonyms of TrustAssessment.
- Framework-specific assurance levels map to Identity Evidence `AssuranceAssessment` dimensions/values rather than replacing it.
- LegalIdentity/PID/GovernmentAttestation/IdentityServiceProvider belong to Government Identity and do not redefine IdentitySubject/DigitalIdentity.
- Accreditation, Certification and EcosystemParticipation belong to Trust Governance and MUST NOT be modeled as Enrollment or CredentialStatus.
- TrustReference is only an alignment hook from Core semantics to external trust/governance constructs.

### Minimum P04 scenario
Government identity establishment composes Identity Representation → Identity Evidence → Identity Establishment → Credential Management → Trust Governance → Government Identity.

## Privacy / consent boundary contract
CM4DI MAY represent that a disclosure/presentation/operation was authorized where a CQ needs it. It MUST NOT import a full consent, purpose, data-protection, retention or privacy-policy ontology into Core. Profile mappings may link to external consent/privacy vocabularies.

## External social-identity contract
- SocialLogin → P01 federation/authentication mapping.
- Affiliation/Membership may appear as Claim/IdentityAttribute values and link to external organization vocabularies.
- SocialIdentity, RoleIdentity, Persona, Reputation, Salience, SocialPerception and ContextCollapse remain outside CM4DI except explicit bridge mappings.

## Profile conformance rule
A profile is conformant only if:
1. it reuses Domain/Bounded Context concept meanings without redefining identity criteria;
2. it supplies rigid role players for abstract Core roleMixins when instantiated;
3. it declares every specialization/mapping explicitly;
4. it preserves anti-conflation constraints;
5. it does not promote a profile concept into Core or a Domain merely for implementation convenience;
6. it can answer profile-specific CQs using the relevant Bounded Contexts;
7. it does not assume Profile = Domain = Bounded Context = OWL module.