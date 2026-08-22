# P01 — Enterprise Identity Profile

**Legacy label:** Enterprise / Federation  
**DDD status:** Cross-domain integration Profile; not a Domain or Bounded Context.

## Purpose
Represent enterprise IAM, federation, SSO, provisioning, accounts, sessions and operational authorization constructs without importing vendor-specific semantics into the CM4DI Core.

## Domain composition
P01 composes Identity Representation, Identity Information, Identity Evidence, Authentication, Authorization, Identity Administration, Federation and Trust Governance. Canonical ownership is defined by the DDD registries; P01 does not own these problem-space boundaries.

## Core and Domain reuse
- `Account` and `UserProfile` belong to Identity Administration and are managed representations/records about an `IdentitySubject`; neither is the subject.
- `Application` belongs primarily to Identity Administration and may play `Party`, `RelyingParty`, `Principal` or `Resource` roles depending on interaction.
- Authentication reuses the Authentication Context; P01 `Session` belongs to Authentication and remains independent from `AuthenticationResult`.
- P01 `PermissionBundle` belongs to Authorization and groups `Permission`; operational IAM role labels never map to UFO social `Role` by name.
- `Provisioning` belongs to Identity Administration and is distinct from Identity Establishment `Enrollment` and `IdentityProofing`.
- `AttributeMapping` and `IdentitySource` belong to Identity Administration and connect to Identity Information / Identity Evidence provenance.
- `Federation`, `FederationConnection`, `IdentityBroker` and `RelyingParty` are governed through the Federation Context.

## Profile concepts
P01 contributes 20 governed concepts in `PROFILE_CONCEPT_REGISTRY_v2.csv`. Their primary Domain assignments are governed independently in `../ddd/CONCEPT_DOMAIN_ASSIGNMENT_v2.csv`.

## Representative external alignments
- AWS IAM Identity Center / IAM: account assignments, permission sets, roles and temporary sessions map pragmatically to Identity Administration, Authorization and Authentication concepts.
- Microsoft Entra: application object -> `ApplicationRegistration`; service principal is handled primarily in Workload Identity; Conditional Access -> `AccessPolicy` + `AccessCondition` + `AuthorizationContext`.
- Google Cloud IAM: principal -> `Principal`; role -> `PermissionBundle`; role binding -> `AccessGrant`.
- Okta/Auth0/PingOne/Keycloak/ZITADEL/authentik: user/account/profile/directory/broker/provisioning/session constructs map through explicit implementation mappings.
- SAML/OIDC/OpenID Federation: provider/connection/assertion constructs map across Federation, Authentication, Identity Information and Trust Governance as appropriate.

## Anti-conflation invariants
`Account != IdentitySubject`; `Session != AuthenticationResult`; `AdministrativeDomain != IdentityContext`; `IdentitySource != IdentityProvider`; `Provisioning != Enrollment`; `IAM Role != UFO Role`; `Application != ApplicationRegistration`; `Federation != FederationConnection`.

## Minimum scenario
Employee identity composes Identity Representation → Identity Administration → Federation → Authentication → Authorization. Trust Governance may be added when federation participation/chain requirements apply.

## Wave-7 formalization expectation
Wave 7 MUST derive OWL packaging from the DDD Context Map and dependency analysis. P01 remains a profile/view and is not automatically one OWL module. Vendor mappings remain mapping artifacts rather than OWL equivalences unless independently justified.