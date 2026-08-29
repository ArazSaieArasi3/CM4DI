# Keycloak Semantic Benchmark — pass 1

Issue: #82. Evidence role: operational implementation benchmark, not ontology authority.

## Current authoritative baseline
Current Keycloak Server Administration Guide reports version **26.7.2** and documents realms, users, groups, roles, sessions, identity brokering, user federation, authentication flows, protocol mappers, service accounts and fine-grained authorization. Source: https://www.keycloak.org/docs/latest/server_admin/

## High-value semantic findings

### Realm is an Administrative Domain
A realm is an isolated administrative space that manages users, credentials, roles, groups and clients. This strongly reinforces `CM4DI-C1006 AdministrativeDomain`. It must not be mapped to `IdentityContext`, because the latter is the semantic situation in which identity representation is interpreted rather than an administrative partition.

### User is a managed representation, not the real-world subject
The Keycloak `User` object combines account/profile/credential associations. Its closest neutral interpretation is a managed `Account` plus `UserProfile` representing an `IdentitySubject`. This validates the existing CM4DI anti-conflation rule `IdentitySubject != Account != UserProfile`.

### Identity-provider federation differs from user federation
Keycloak makes an unusually useful operational distinction:
- **Identity provider federation/brokering** delegates authentication to external OIDC/SAML/social IdPs.
- **User federation** connects Keycloak to LDAP/Active Directory or custom user stores for credential validation and identity-information retrieval/synchronization.

This directly reinforces `Federation != Provisioning` and `IdentityBroker/FederationConnection != IdentitySource/IdentityStore/ProvisioningConnection`.

### Account linking is co-reference, not equality
Identity brokering allows an internal account to be linked to one or more external-provider identities. This is evidence for CM4DI `linkedAccount` as a correlation/co-reference relation. The operational link can be created and removed and therefore must not be represented as `owl:sameAs` or as proof that two account objects are the same ontological individual.

### Session is a temporal relation, not an authentication result
Keycloak creates a session after login and tracks participating clients, timeouts, logout and revocation. This reinforces `Session != AuthenticationResult` and supports investigation of an explicit `establishedBy(Authentication)` relation and generic session lifecycle pattern.

### IAM roles are not UFO Roles
Realm/client roles are assignable authorization constructs, can be composite and can be inherited through group membership. Their most stable CM4DI interpretation is `PermissionBundle` plus `AccessGrant`; they are not anti-rigid ontological roles in the UFO sense. Composite-role inclusion also must not be mistaken for a subclass relation.

### Client is primarily an application registration
A Keycloak client is configuration for an OIDC/SAML relying application/service. It aligns more strongly to `ApplicationRegistration` than to the software `Application` entity itself. This distinction is important for the relational model and formal ontology.

### Authorization Services expose a richer implementation model
Resources, scopes, policies and permissions show why CM4DI should preserve a small neutral authorization kernel while mapping richer policy-engine constructs in a profile/neighbor layer. In particular, a Keycloak permission object can combine resource/scope targeting with policies; it is not a simple one-to-one match to the CM4DI normative `Permission` concept.

## Relation discoveries
1. `realm manages account/application/role/group` — implementation ownership relation.
2. `user assigned role` — AccessGrant pattern.
3. `user memberOf group` — GroupMembership.
4. `group carries role mappings` — indirect grant/inheritance pattern.
5. `client has service account` — application-registration to non-human account association.
6. `broker links local account to external provider identity` — linkedAccount with federation provenance.
7. `user federation provider connects external store to local representation` — IdentitySource/IdentityStore/ProvisioningConnection pattern.
8. `successful login establishes session` — candidate relation not yet explicit enough in CM4DI.
9. `protocol mapper transforms source attributes/roles into outgoing claims` — AttributeMapping with provenance.
10. `authorization permission binds resource/scope to policies` — compound authorization configuration pattern.

## Lifecycle discoveries
- local user/account create/update/disable/delete;
- external/federated link create/unlink;
- credential registration/update/reset;
- required-action scheduling/completion;
- session create/timeout/logout/revoke;
- role/group assignment and removal;
- client/service-account lifecycle;
- user-federation synchronization/import lifecycle.

These reinforce the lifecycle ledger and suggest that **AccountStatus, Session lifecycle, Authenticator lifecycle and AccountLinking provenance** deserve explicit cross-product comparison before #66.

## DDD verdict
No Domain or Bounded Context rename/split/merge is justified by the current Keycloak pass. In fact the implementation supports the current separation among:
- Identity Administration Context;
- Federation Context;
- Authentication Context;
- Authorization Context;
- Workload Identity Context.

The name-governance rule remains satisfied: no canonical Domain name contains `and`, `&`, or a slash-composed semantic center.

## New discovery opportunities
- B2B `Organization` should be compared with Auth0/WorkOS/Clerk/Frontegg and W3C ORG before any CM4DI concept is introduced.
- Fine-grained admin authorization is a useful scenario for AccessGrant/PermissionBundle/AccessPolicy evaluation.
- Required Actions provide evidence for a reusable identity-lifecycle workflow pattern, but are too implementation-specific to promote yet.
- Keycloak Admin Events are useful provenance/evaluation evidence and strengthen the PROV-O neighbor-alignment case.

## Remaining before closing #82
Authorization Services deep extraction; exact API/schema/state transitions; repository implementation sampling; organizations feature; credential/passkey lifecycle; exact CM4DI relation IDs and CQs; source locator completion; regression disposition in #66.
