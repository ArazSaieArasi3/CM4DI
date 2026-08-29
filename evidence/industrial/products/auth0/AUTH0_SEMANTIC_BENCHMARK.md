# Auth0 Semantic Benchmark — pass 1

Issue: #80. Evidence role: operational CIAM benchmark, not ontology authority.

## Authoritative sources used in pass 1
- User Profiles: https://auth0.com/docs/manage-users/user-accounts/user-profiles
- Organizations: https://auth0.com/docs/manage-users/organizations/organizations-overview
- Identify Users: https://auth0.com/docs/manage-users/user-accounts/identify-users
- Account linking API: https://auth0.com/docs/api/management/v2/users/post-identities
- Authentication/connections: https://auth0.com/docs/authenticate

## High-value semantic findings

### Auth0 User is a tenant-local managed representation
Auth0 guarantees `user_id` uniqueness within a tenant and normalizes data from database, social and enterprise identity providers into a user profile. Therefore the Auth0 User is best interpreted as an `Account` with a `UserProfile`, not as the real-world `IdentitySubject` itself.

### Connection is semantically overloaded
Auth0 calls user-data/authentication integrations **connections**. A database connection, an enterprise SAML connection and a social connection are all “connections,” but neutral ontology semantics differ:
- database connection → IdentityStore / IdentitySource / ProvisioningConnection pattern;
- enterprise/social connection → FederationConnection plus possible IdentitySource role;
- connected-account use → account-linking integration.

This strongly validates CM4DI’s decision not to create a generic vendor-neutral `Connection` Core class.

### Account linking strongly validates co-reference over equality
Auth0 explicitly links two user accounts into a **primary/secondary relationship**, after which the primary profile has multiple identity entries. Auth0 also states that it does **not merge user profile attributes from multiple providers** and sources core profile data from the primary/first provider. This is excellent operational evidence that:
- account link ≠ identity equality;
- account link has direction/asymmetry;
- identity-provider provenance remains relevant after linking;
- `owl:sameAs` would be too strong for a generic identity-link operation.

This supports retaining `linkedAccount` and investigating a richer `AccountLinking` event/relator with provenance and lifecycle.

### `user_id` reinforces scoped Identifier semantics
A user identifier is unique within an Auth0 tenant, frequently provider-qualified, but not guaranteed to be stable or equivalent across tenants. This is direct operational support for CM4DI `Identifier` being scheme/scope/context dependent rather than a globally identifying intrinsic property.

### UserProfile has provenance layers
The normalized profile can include:
- root/normalized attributes from an identity provider;
- read-only identity-provider attributes;
- user-managed `user_metadata`;
- application/admin-managed `app_metadata`.

This exposes a useful provenance distinction. `IdentityAttribute` or `Claim` should not imply that every profile field is verified or authoritative. `AuthoritativeIdentitySource` must be scoped to specific information.

### Organizations reveal an adjacent B2B organizational model
Auth0 Organizations have members, enabled connections and member roles. This is not equivalent to CM4DI `AccessGroup` and should not become a general organization ontology inside CM4DI. It is a strong candidate for bridge/reuse with W3C ORG and for a B2B identity pattern shared with WorkOS, Clerk, Frontegg and Keycloak Organizations.

### Device and authenticator evidence suggests additional relation/lifecycle analysis
Auth0 User Details exposes passkeys, MFA factors, devices and login history. Device authorization can link a device to an account and refresh token. These patterns reinforce the need to distinguish:
- Device vs DeviceIdentityRecord;
- Authenticator vs Device;
- Account-device association;
- RefreshToken/temporary credential vs Session.

## Relation discoveries
1. tenant contains/manages user accounts, applications and connections;
2. user account has normalized profile;
3. profile attribute sourced from connection/provider;
4. user account has multiple provider identity entries;
5. primary account links secondary account/identity;
6. organization has members and enabled connections;
7. organization member assigned role;
8. application enabled for connection;
9. device linked to account/refresh token context;
10. passkey/MFA factor enrolled for account authentication.

## Lifecycle discoveries
- create/update/delete/block/unblock user account;
- create/update/delete connection;
- link/unlink account identities;
- organization/member/role assignment lifecycle;
- factor/passkey enrollment/removal;
- device association/unlink;
- refresh-token issue/rotation/revocation;
- external profile cache refresh on authentication.

## Candidate semantic deltas to test in #66
1. **AccountStatus** mode or a neutral account-lifecycle pattern may be missing.
2. **AccountLinking** event/relator may be needed if provenance/lifecycle cannot be represented robustly by `linkedAccount` alone.
3. scoped **authoritativeFor(attribute/claim)** relation for `AuthoritativeIdentitySource` may deserve formalization.
4. B2B Organization/Membership should likely be a neighbor-ontology bridge, not a new Core area.
5. Account-device association should be tested against Device Identity CQs.

## DDD verdict
No Domain rename is justified. Auth0 reinforces separation among Identity Administration, Federation, Authentication, Authorization and Device Identity. `Social Login` remains a Federation/Authentication integration and is not evidence for merging SemSocialIdentity into CM4DI.

## New discovery opportunities
- Build a cross-product **Account Linking Benchmark** across Auth0, Okta, Keycloak and semDIM.
- Build a **B2B Organization Identity Pattern** benchmark across Auth0, WorkOS, Clerk, Frontegg and Keycloak, aligned with W3C ORG.
- Build an **Attribute Provenance Matrix** across Auth0, Okta UD, SCIM and Entra.
- Evaluate Token Vault / connected-account semantics as credential custody rather than identity representation.

## Remaining before closing #80
Exact Organizations/roles lifecycle; RBAC/permissions; session/cookie/token lifecycle; Actions and Token Vault; passkey/MFA flow details; Management API schema; CQ mapping; final #66 disposition.
