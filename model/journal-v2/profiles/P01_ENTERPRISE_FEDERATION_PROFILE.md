# P01 — Enterprise / Federation Profile

## Purpose
Represent enterprise IAM, federation, SSO, provisioning, accounts, sessions and operational authorization constructs without importing vendor-specific semantics into the CM4DI Core.

## Core reuse
- `Account` and `UserProfile` are managed representations/records about an `IdentitySubject`; neither is the subject.
- `Application` may play Core `Party`, `RelyingParty`, `Principal` or `Resource` roles depending on interaction.
- Authentication reuses Core `Authentication` and `AuthenticationResult`; P01 `Session` is independent.
- P01 `PermissionBundle` groups Core `Permission`; operational IAM role labels map here and never to UFO social `Role` by name.
- `Provisioning` is distinct from Core `Enrollment`, `IdentityProofing` and `Authentication`.
- `AttributeMapping` and `IdentitySource` connect to Core Claim/IdentityAttribute provenance.

## Profile concepts
P01 contributes 20 governed concepts in `PROFILE_CONCEPT_REGISTRY_v2.csv`: Account, UserProfile, IdentitySource, AuthoritativeIdentitySource, IdentityStore, AdministrativeDomain, Application, ApplicationRegistration, Federation, FederationConnection, IdentityBroker, Provisioning, ProvisioningConnection, AttributeMapping, Session, PermissionBundle, AccessPolicy, AccessCondition, AccessGroup and GroupMembership.

## Representative external alignments
- AWS IAM Identity Center / IAM: account assignments, permission sets, roles and temporary sessions map pragmatically to `Account`, `AccessGrant`, `PermissionBundle`, Core `Principal`, and P01 `Session`.
- Microsoft Entra: application object -> `ApplicationRegistration`; service principal is handled primarily in P03 as a principal/application-instance pattern; Conditional Access -> `AccessPolicy` + `AccessCondition` + Core `AuthorizationContext`.
- Google Cloud IAM: principal -> Core `Principal`; role -> P01 `PermissionBundle`; role binding -> Core `AccessGrant`.
- Okta/Auth0/PingOne/Keycloak/ZITADEL/authentik: user/account/profile/directory/broker/provisioning/session constructs map to corresponding P01 concepts with implementation rather than exact-equivalence predicates.
- SAML/OIDC/OpenID Federation: protocol provider/connection/assertion concepts map to P01 Federation/FederationConnection and Core interaction roles/Claim/Authentication semantics.

## Anti-conflation invariants
`Account != IdentitySubject`; `Session != AuthenticationResult`; `AdministrativeDomain != IdentityContext`; `IdentitySource != IdentityProvider`; `Provisioning != Enrollment`; `IAM Role != UFO Role`; `Application != ApplicationRegistration`; `Federation != FederationConnection`; `User federation != authentication federation`.

## Minimum scenario
Employee person plays Core `IdentitySubject`; Entra/Okta-style `Account` represents the subject in an `AdministrativeDomain`; a `FederationConnection` enables federated `Authentication`; a successful result establishes a P01 `Session`; the account/application representation plays `Principal`; `AccessGrant` connects the principal to Core `Permission` or P01 `PermissionBundle`; Core `Authorization` evaluates the runtime request.

## Wave-7 formalization expectation
P01 becomes a separate ontology module importing/reusing the Core. Vendor mappings remain mapping artifacts rather than OWL class equivalences unless a mapping has independently justified exact semantics.