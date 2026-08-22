# CM4DI Journal V2 — Profile Domain Contracts

## Purpose
Profiles are cross-domain integration views. They are not DDD Domains, not Bounded Contexts, and not predetermined OWL modules. Stable profile IDs P01–P04 are preserved; canonical display labels are refined while historical labels remain aliases for lineage.

## Canonical profile labels
- **P01 Enterprise Identity Profile** — legacy label: Enterprise / Federation.
- **P02 Verifiable Credential Profile** — legacy label: Wallet / Verifiable Credentials.
- **P03 Technical Identity Profile** — legacy label: Machine / Workload / Device / Agent.
- **P04 Governed Identity Profile** — legacy label: Trust / Assurance / Government.

## P01 Enterprise Identity Profile
Composes Identity Representation, Identity Information, Identity Evidence, Authentication, Authorization, Identity Administration, Federation and Trust Governance.

Required boundaries:
- Account and UserProfile remain Identity Administration constructs, not IdentitySubject kinds.
- Provisioning belongs to Identity Administration and remains distinct from Identity Establishment Enrollment.
- Federation belongs to the Federation subdomain and consumes Authentication and Trust Governance contracts.
- Session belongs to Authentication, not to Federation and not to AuthenticationResult.
- IAM roles and permission sets map into Authorization PermissionBundle/Permission semantics, never UFO role stereotypes by lexical similarity.

## P02 Verifiable Credential Profile
Composes Identity Representation, Identity Information, Identity Evidence, Credential Management, Credential Exchange and Trust Governance.

Required boundaries:
- Issuer belongs primarily to Credential Management; Holder and CredentialPresentationVerifier belong to Credential Exchange.
- Holder is not CredentialSubject by definition.
- CredentialPresentation is not Authentication.
- DID-like identifiers map to Identifier; controller and verification methods remain Credential Exchange constructs.
- Cryptographic proofs may play Core Evidence/Proof roles without redefining those roles.
- Registry/trusted-status semantics must be translated explicitly when Credential Exchange touches Trust Governance.

## P03 Technical Identity Profile
Composes Identity Representation, Identity Evidence, Credential Management, Authentication, Authorization, Identity Administration, Workload Identity, Device Identity, Agent Identity and Trust Governance.

Required boundaries:
- There is no `MachineIdentity` superclass.
- Workload, Device and SoftwareAgent/AIAgent are independently modeled identity-bearing kinds in separate subdomains.
- ServiceAccount and ServicePrincipal remain Workload Identity constructs with explicit links to Identity Administration and Authorization semantics.
- Device may play IdentitySubject, Principal or Authenticator without collapsing those roles into Device identity.
- SVID and TemporaryCredential reuse Credential Management semantics.
- Workload/Node Attestation uses Identity Evidence and IdentityBinding.
- Agent delegated access reuses Authorization Delegation; sponsor/accountability links may consume Trust Governance semantics.

## P04 Governed Identity Profile
Composes Identity Representation, Identity Information, Identity Evidence, Identity Establishment, Credential Management, Trust Governance and Government Identity.

Required boundaries:
- TrustFramework, TrustRegistry, TrustedList, TrustAnchor and TrustChain remain Trust Governance constructs.
- LegalIdentity, PersonIdentificationData, GovernmentAttestation and governed IdentityServiceProvider remain Government Identity constructs.
- TrustAssessment is not certification, accreditation, participation status or cryptographic validation.
- Government proofing reuses Identity Establishment and Identity Evidence semantics.
- Government credentials may reuse Credential Management and may be presented through P02, but Wallet is not a Government Identity concept.

## Cross-profile rule
A scenario may compose more than one profile. This does not merge their source Domains or Bounded Contexts. EUDI, workload federation and agent authorization are explicitly cross-profile scenarios.

## External model rule
W3C, OpenID, ISO, NIST, eIDAS/EUDI, SPIFFE, cloud IAM and vendor schemas enter CM4DI through governed mappings. When their language conflicts with canonical CM4DI semantics, an Anticorruption Layer translation is required rather than changing the internal Domain model.