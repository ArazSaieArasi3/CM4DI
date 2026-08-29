# External Identity Service Adapters

Status: **architecture candidate derived from current DDD and industrial discovery; not a deployment freeze**.

## Purpose
Define how CM4DI-aligned applications can integrate external IAM, SSO, directory, wallet, trust and government-identity services without allowing vendor/protocol vocabularies to redefine the canonical domain model.

## Anticorruption Layer rule
Every external adapter translates between an external system's vocabulary and CM4DI's governed concepts/relations. Direct persistence or propagation of vendor object names into the canonical domain model is avoided unless the construct is explicitly governed as an implementation/profile concept.

## Adapter families

| Adapter family | Representative external systems | CM4DI contexts | Translation responsibility |
|---|---|---|---|
| Workforce IAM Adapter | Microsoft Entra ID, Okta, Google Cloud Identity, PingOne, Keycloak | Identity Administration; Authentication; Federation; Authorization | User/account/profile/source/app/session/role/assignment normalization |
| AWS Access Adapter | AWS IAM, IAM Identity Center, STS | Authorization; Workload Identity; Federation | Principal/policy/permission-set/role-assumption/account-assignment to Principal, PermissionBundle, AccessGrant, TemporaryCredential mappings |
| Google Federation Adapter | Workforce Identity Federation, Workload Identity Federation, Cloud IAM | Federation; Workload Identity; Authorization | external subject/attribute/provider/pool/token exchange mapping without implying local account provisioning |
| Entra Workload Adapter | Managed Identities, service principals | Workload Identity; Identity Administration; Authorization | Application vs ServicePrincipal vs ManagedIdentity distinction; role assignments to AccessGrant |
| Directory Adapter | LDAP, Active Directory, SCIM, Okta Universal Directory | Identity Administration; Identity Information | directory entry/user/group/profile/source/provisioning mappings |
| OIDC Adapter | OpenID Connect providers/clients | Authentication; Federation; Identity Information | subject identifier, claims, IdP/RP, authentication flow and session metadata normalization |
| SAML Adapter | SAML IdP/SP ecosystems | Authentication; Federation; Identity Information | assertion, subject/name identifiers and federation-role mappings |
| VC Issuance Adapter | OpenID4VCI issuers, EUDI providers | Credential Lifecycle; Credential Exchange | issuer, credential offer/request/issuance and status mappings |
| VC Presentation Adapter | OpenID4VP, EUDI wallet/verifier | Credential Exchange; Identity Evidence | wallet/holder/verifier/request/presentation/proof mappings |
| Workload Identity Adapter | SPIFFE/SPIRE, cloud workload federation | Workload Identity; Identity Evidence; Credential Lifecycle | workload, attestation, SPIFFE ID, SVID, TrustDomain and short-lived credential mappings |
| Trust Framework Adapter | EUDI, PCTF, UK DVS, Australia | Trust Governance; Government Identity | framework/registry/trusted-list/participation/conformance/legal-role translation |
| Government Identity Adapter | EUDI PID/EAA, MOSIP, national ID services | Government Identity; Identity Assurance; Credential Lifecycle | legal identity, PID, attestation, proofing/registration and service-provider mappings |

## Mapping discipline examples

- AWS `Role` is not mapped to a generic UFO Role. Depending on context it can participate as Principal and carry/derive PermissionBundle semantics.
- Entra `Tenant`, Keycloak `Realm`, Okta `Org`, ZITADEL `Organization` and PingOne `Environment` map to implementations of AdministrativeDomain, not IdentityContext.
- Google Workforce Identity Federation Provider/Pool objects configure Federation; the absence of synchronized user accounts is preserved rather than normalized away.
- External IdP account linking maps to `linkedAccount` co-reference/correlation semantics and never to `owl:sameAs` by default.
- SCIM `User` is an interoperability resource representation, not the IdentitySubject itself.
- EUDI `PID`/`EAA` constructs map through Government Identity/Credential contexts without redefining the generic Credential or Claim core.

## Adapter contract metadata
Every production/reference adapter should declare:

- external product/standard and exact version/status;
- supported operations;
- source object type;
- target CM4DI concept/relation IDs;
- mapping cardinality and lossiness;
- identity/equality assumptions;
- lifecycle semantics;
- trust/provenance source;
- error/unknown-term handling;
- security/privacy considerations;
- test scenarios/CQs;
- last verified date.

## Architecture implications
Adapters are infrastructure/integration components. They may be deployed next to a Bounded Context, shared behind an integration gateway, or embedded in an application service. Their deployment does not change Domain ownership.

Issue #76 will later connect these adapters to feature/user-story/test traceability and ATAM-lite quality scenarios. Source Completeness #60/#66 remains authoritative for semantic changes.