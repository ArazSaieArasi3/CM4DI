# CM4DI Journal V2 — Enterprise / Federated Profile Decision Support

**Status:** Gate-B decision support only; no ontology admission.

## 1. Main operational result

Enterprise IAM confirms that digital identity systems are not well represented by a flat actor–credential–authentication model. Mature systems consistently separate:

`Identity Subject → Account/Profile Representation → Identity Source → Federation/Provisioning → Authentication → Session → Principal → Access Grant/Policy → Resource`

Not every deployment contains every layer, and a single product may implement several layers. The ontology must therefore model **functions and semantic distinctions**, not vendor components.

## 2. Highest-priority Gate-B candidates

### A. Account / platform-local identity representation
Operational recurrence is very high. A person, workload or external identity is usually represented by one or more managed account objects in directories/tenants/applications. `Account` should be tested as distinct from both `IdentitySubject` and `DigitalIdentity`.

**Evidence examples:** Cognito user profile, Entra user/guest/service-principal objects, Okta user, Auth0 user, PingOne user identity, Keycloak user, ZITADEL user.

### B. Principal
Authorization engines operate on principals that may represent people, groups, service accounts or federated identities. A Principal is therefore likely an anti-rigid role/authorization representation rather than a synonym for person or IdentitySubject.

### C. Session
Authentication results are routinely followed by a temporally extended session with independent issue, expiry, refresh and revocation semantics. `Session` should not be collapsed into `AuthenticationResult`.

### D. Access Grant / Assignment
Durable assignments connect a principal/account/group to permissions or permission bundles in a resource/scope. This is distinct from the runtime `Authorization` event. AWS assignments, Entra role/app assignments, Google role bindings, Okta app assignments and ZITADEL role assignments converge on this pattern.

### E. Permission and Permission Bundle
Authorization requires a neutral unit for allowed actions, while operational `role`, `permission set`, `scope`, and similar terms frequently package permissions. `PermissionBundle` is the safest normalization target for many vendor IAM-role constructs; it must not be confused with UFO Role.

### F. Identity Source / Authoritative Identity Source
AWS, PingOne, Okta, Keycloak and authentik independently show that the system authoritative for identity data can differ from the system performing authentication or consuming the identity. This distinction is essential for federation/provisioning traceability.

### G. Attribute Mapping / Provenance
Federation and provisioning transform claims/attributes between source and target schemas. This operational evidence reinforces the government-wave `AttributeProvenance` candidate and argues for first-class traceable mappings rather than free-text mapping notes.

## 3. Strong Enterprise/Federated Profile candidates

- Identity Store / Directory
- Group and Group Membership
- Administrative Domain / Tenant / Realm abstraction
- Application / Client
- Federation Connection
- Identity Broker / Intermediary
- Provisioning and Deprovisioning
- Provisioning Connection
- Provisioning Scope / Rule
- Account Lifecycle State
- Session Lifecycle
- Temporary Credential
- Access Policy / Condition
- Application Account
- Guest / External Account status
- JIT Provisioning
- Dynamic Group Membership Rule

These are operationally important but do not all justify Core admission.

## 4. Candidates explicitly deferred to Issue #6

The following recur strongly but require dedicated non-human ontological analysis before admission:

- Workload Identity
- Service Account
- Service Principal
- Managed Identity
- Device Identity
- workload federation / service-account impersonation distinctions
- AI-agent identity and delegated agent principal patterns

Issue #5 records their operational evidence but does not settle their UFO categories.

## 5. Existing CM4DI concepts requiring semantic review

### `IdentityProvider`
Operational systems support narrowing it to an **authentication/federation provider role**. It should not silently cover directory authority, attribute source, provisioning source, wallet provider and governance authority.

### `RelyingParty`
The concept remains useful but should likely be an anti-rigid role played by an organization/application/service in a transaction, rather than a rigid actor subtype. Enterprise clients/applications can play RP, resource server or other roles in different contexts.

### `Subscriber`
Operational account-holder and enterprise workforce semantics do not consistently use a Subscriber role. Retention in Core should be justified by NIST/credential enrollment semantics rather than generalized to all users/holders/accounts.

### `DigitalIdentity`
Do not equate vendor user/account/profile objects with DigitalIdentity. Gate B must specify whether an Account **represents** an IdentitySubject, contains/realizes identity information, participates in a DigitalIdentity, or is itself one implementation form of DigitalIdentity under defined conditions.

### `Enrollment`
Enterprise provisioning and JIT account creation are distinct. `Enrollment` must not become a catch-all for account creation/synchronization.

### `AuthenticationResult`
A successful result may establish a `Session`; the result and the temporally extended session remain distinct.

### `Authorization` / `AuthorizationResult`
Standards-wave `Resource`, `Action`, `Context`, `Decision` are operationally confirmed. Enterprise IAM adds **durable grant/assignment** semantics outside the runtime authorization event.

### `Credential`
Enterprise IAM uses password credentials, authenticator credentials, access/ID tokens, role-session credentials, API/service-account credentials and certificates. The generic concept needs a clear identity criterion and taxonomy so operational artifacts are not all forced into one undifferentiated class.

## 6. Cross-wave convergence before Gate B

| Semantic theme | Standards wave | Government/trust wave | Enterprise IAM wave | Current confidence |
|---|---|---|---|---|
| Identity proofing/evidence | Strong | Strong | Indirect | High |
| Resource/action/decision authorization | Strong | Medium | Strong | Very high |
| Federation as explicit construct | Strong | Strong | Very strong | Very high |
| Trust framework/registry/anchor separation | Strong | Very strong | Supporting | Very high |
| Attribute provenance/binding | Medium | Very strong | Very strong | Very high |
| Lifecycle separation | Strong | Very strong | Very strong | Very high |
| Account/profile representation | Weak | Medium | Very strong | High; needs academic/UFO check |
| Principal | Strong in authorization specs | Medium | Very strong | High; needs ontological categorization |
| Session | Medium | Low | Very strong | High; profile/Core boundary unresolved |
| Durable access grant/assignment | Medium | Medium | Very strong | High |
| Administrative domain/tenant/realm | Low | Medium | Very strong | Profile-level confidence high |
| Non-human identity | Normative support | Limited | Strong | Requires Issue #6 |

## 7. Recommended Enterprise/Federated Profile skeleton for later Gate B/C

This is **not** a frozen module. It is a candidate grouping to reduce future rework.

### Identity representation
- Account
- UserProfile / AccountProfile
- ExternalIdentityReference
- AccountLink
- AdministrativeDomain

### Source and federation
- IdentitySource
- AuthoritativeIdentitySource
- IdentityStore/Directory
- FederationConnection
- IdentityBroker / Intermediary
- AttributeMapping

### Provisioning and lifecycle
- Provisioning
- ProvisioningConnection
- ProvisioningRule/Scope
- AccountLifecycleState
- JITProvisioning

### Authentication continuity
- Session
- SessionLifecycle
- TemporaryCredential (profile subtype pending credential taxonomy)

### Authorization administration
- Principal
- Permission
- PermissionBundle
- AccessGrant/Assignment
- AccessPolicy
- AccessCondition
- Group / GroupMembership
- Application / Client / Resource role mappings

## 8. Boundary principle

The Enterprise/Federated Profile should explain **how identities are represented, sourced, federated, synchronized, authenticated and granted access across administrative domains**. It should not become a vendor configuration ontology, full IGA product model, or complete access-control policy language.