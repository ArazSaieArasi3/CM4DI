# CM4DI DDD Capability Map

Status: **candidate downstream realization of the governed DDD model; not a product/microservice freeze**.

## Governing rule
`Domain != Bounded Context != Profile != Product != Service != Database != OWL Module`.

Canonical Domain and Bounded Context labels do not contain `and`, `&`, or slash-composed semantic centers.

## Capability map

| Domain | Bounded Context | Core business/problem capability | Supporting capabilities | Governed concepts driving the capability |
|---|---|---|---|---|
| Identity Representation | Identity Semantics Context | Represent an identity-bearing subject in a scoped digital form | identifier management; context scoping; subject-reference resolution | Party; IdentitySubject; DigitalIdentity; Identifier; IdentityContext |
| Identity Information | Identity Semantics Context | Represent identity-related facts and assertions | attribute management; claim construction; semantic normalization | IdentityAttribute; Claim |
| Identity Evidence | Identity Assurance Context | Collect, classify and assess evidence supporting identity assertions/bindings | proof handling; evidence provenance; assurance assessment; verification | Evidence; Proof; IdentityBinding; AssuranceAssessment; Verifier |
| Identity Establishment | Identity Assurance Context | Establish confidence in subject identity and create managed identity relationships | proofing workflow; enrollment; evidence resolution | IdentityProofing; Enrollment; IdentityBinding |
| Credential Management | Credential Lifecycle Context | Issue and manage lifecycle/status of credentials | issuance; status update; suspension/revocation/expiry tracking | Credential; CredentialStatus; CredentialLifecycleEvent; CredentialIssuance; Issuer |
| Authentication | Authentication Context | Verify claimant/entity/authenticator control and maintain post-authentication context | authenticator lifecycle integration; authentication result; session management | Authentication; Authenticator; AuthenticationResult; Session |
| Authorization | Authorization Context | Decide and govern permitted actions on protected resources | request evaluation; permissions; grants; delegation; policy/condition handling; access grouping | Authorization; AuthorizationRequest; AuthorizationContext; AuthorizationResult; Principal; Resource; Action; Permission; AccessGrant; Delegation; PermissionBundle; AccessPolicy; AccessCondition; AccessGroup; GroupMembership |
| Identity Administration | Identity Administration Context | Administer platform-local identity representations and application relationships | account/profile management; identity-source integration; store administration; provisioning; application registration; attribute mapping | Account; UserProfile; IdentitySource; AuthoritativeIdentitySource; IdentityStore; AdministrativeDomain; Application; ApplicationRegistration; Provisioning; ProvisioningConnection; AttributeMapping |
| Federation | Federation Context | Establish cross-domain identity relationships and federated sign-in/identity exchange | broker configuration; relying-party integration; federation metadata/connection lifecycle | Federation; FederationConnection; IdentityBroker; RelyingParty |
| Credential Exchange | Credential Exchange Context | Request, hold, selectively disclose, present and verify credential-derived information | wallet/holder interaction; presentation request; controller/verification method; registry lookup | Holder; CredentialPresentationVerifier; Wallet; HolderService; CredentialPresentation; PresentationRequest; Controller; VerificationMethod; VerifiableDataRegistry; SelectiveDisclosure; VerifiablePresentation |
| Workload Identity | Workload Identity Context | Establish and operate identity for runtime workloads and services | workload/node attestation; service account/principal mapping; managed identity; short-lived credential/token exchange; trust-domain verification | Workload; RuntimeInstance; ServiceAccount; ServicePrincipal; ManagedIdentity; NodeAttestation; WorkloadAttestation; TrustDomain; TrustBundle; SVID; TemporaryCredential; TokenExchange |
| Device Identity | Device Identity Context | Represent devices as identity-bearing entities and manage device identity records | device registration; device-record lifecycle; authentication/authorization role integration | Device; DeviceIdentityRecord |
| Agent Identity | Agent Identity Context | Represent software/AI agents as identity-bearing and authorization-capable entities | agent identity registration; sponsor/accountability; delegation integration | SoftwareAgent; AIAgent; AgentIdentity; AgentSponsor; Delegation |
| Trust Governance | Trust Governance Context | Govern trust participation, registries, conformance and trust-reference structures | framework administration; trusted lists; trust anchors/chains; certification; accreditation; participant status | TrustAssessment; TrustReference; TrustFramework; GovernanceFramework; TrustRegistry; TrustedList; TrustAnchor; TrustChain; GovernanceAuthority; Registrar; Regulator; ConformityAssessmentBody; Certification; Accreditation; EcosystemParticipation; ParticipantStatus |
| Government Identity | Government Identity Context | Represent legally recognized identity and regulated identity attestations/services | PID handling; government attestation; regulated identity service-provider integration | LegalIdentity; PersonIdentificationData; GovernmentAttestation; IdentityServiceProvider |

## Cross-context capability flows

### Workforce IAM
Identity Administration → Authentication → Federation → Authorization.

### Customer/CIAM
Identity Administration → Identity Establishment → Authentication → Federation → Authorization, with optional Social Login mapping that remains outside Social Identity semantics.

### Verifiable Credential
Identity Establishment → Credential Management → Credential Exchange → Trust Governance.

### Government Digital Identity
Government Identity → Identity Assurance → Credential Lifecycle → Credential Exchange → Trust Governance.

### Workload Identity
Workload Identity → Identity Assurance → Credential Lifecycle → Authentication/Federation → Authorization.

### AI Agent
Agent Identity → Identity Representation → Delegation/Authorization → Trust Governance; workload infrastructure may be used operationally but does not define the agent semantically.

## Product/architecture implications

- A Bounded Context may be realized by one service, several services, a modular monolith component or an external platform adapter.
- External IAM products are treated as adapters/mapping targets; they do not determine CM4DI Domain ownership.
- Product features must trace to capabilities and governed semantics before implementation.
- Relational tables, APIs and events must preserve stable concept/relation mappings rather than becoming a parallel uncontrolled domain model.

## Current revalidation result
The initial industrial benchmark in `evaluation/DDD_INDUSTRIAL_DISCOVERY_REVALIDATION_2026-08-29.md` found no evidence-based reason to rename, merge or split the current 15 canonical subdomains. Final revalidation occurs in Issue #66 after Source Completeness.