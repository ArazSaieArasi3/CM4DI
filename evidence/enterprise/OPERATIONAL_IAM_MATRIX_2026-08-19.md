# CM4DI Journal V2 — Operational Enterprise / Cloud IAM Matrix

**Review date:** 2026-08-19  
**Scope:** Issue #5 / roadmap D11–D14  
**Method:** bounded semantic benchmark of current official product documentation. Product terminology is evidence for operational patterns, not an ontology vocabulary to import directly.

## 1. Comparative matrix

| Platform / ecosystem | Identity substrate / partition | Federation / authentication | Provisioning / lifecycle | Authorization model | High-value CM4DI implication |
|---|---|---|---|---|---|
| **AWS IAM Identity Center** | Identity source → Identity Center identity store; users/groups | External IdP via SAML; IdP remains authentication authority | SCIM provisions users/groups; assignments can be lost/changed when identity source changes | Permission sets assigned to users/groups and provisioned into AWS accounts as IAM roles | Authentication federation, identity materialization/provisioning and authorization assignment are distinct layers. `IdentitySource` and `Assignment` are strong neutral candidates. |
| **AWS IAM** | IAM users/roles/security principals in AWS account | Role assumption by users/apps/services; federation can obtain temporary credentials | Role and policy lifecycle; temporary role sessions | Permission policies + trust policies; role session carries temporary credentials | AWS `role` is an assumable security identity/context, **not** a UFO social role. Separate `PermissionBundle`, `AccessGrant`, `RoleSession`, and `TemporaryCredential`. |
| **Amazon Cognito** | User pool = application user directory; identity pool = federated identifier/credential broker | User pool is OIDC IdP and can broker social/OIDC/SAML IdPs | signup, confirmation, recovery, disable, migration, group management; federated profile creation/linking | Groups can map to IAM roles; identity pools exchange authenticated/guest identities for temporary AWS credentials | `UserAccount/Profile`, `AccountLink`, `IdentitySourceConnection`, directory vs federated authorization identity, and guest identity patterns recur. |
| **Microsoft Entra ID** | Tenant/directory with user principals, app objects, service principals, device objects | OIDC/SAML/federation; External ID for guests/customers; workload federation | SCIM provisioning; account/service-principal lifecycle; access reviews | Role assignments, app permissions, Conditional Access; service principals/managed identities are security principals | Distinguish **application description** from **tenant-local application/service principal**; human, workload and device identity-bearing objects are different. Detailed non-human taxonomy remains Issue #6. |
| **Google Cloud IAM** | Principals: human accounts/groups, workforce federated principals, service accounts, workload federated principals | Workforce and Workload Identity Federation via OIDC/SAML and other trust mechanisms | Pool/provider configuration and service-account lifecycle; short-lived credentials | Principal + role(permission bundle) + resource + policy binding + optional condition | Strong operational confirmation for `Principal`, `Permission`, `Resource`, `AccessGrant/RoleBinding`, `Policy`, `Condition`; vendor `role` remains a permission bundle, not UFO Role. |
| **Google Identity Platform** | Project/tenant; each tenant has isolated users/providers/configuration | SAML/OIDC/social/password authentication | account creation/deletion, migration, provider/account linking | Application authorization typically uses claims/custom claims/IAM integration | `Tenant/Realm` is an administrative/data-isolation boundary and must not be conflated with CM4DI `IdentityContext`. |
| **Okta Identity Engine** | Universal Directory; user/profile/user type, groups, realms, app user profiles | Okta IdP, inbound IdPs, routing, SAML/OIDC, IdP authenticator | JIT, SCIM provisioning, profile sourcing, activation/suspension/deactivation, app provisioning | App assignments, group rules, roles/policies; IdP/app sessions | Supports `ProfileSource`, `Realm/Tenant`, `AppAssignment`, `GroupMembership`, `Session`, and IdP routing/brokering distinctions. |
| **Auth0** | Tenant, users/profiles, organizations; database/social/enterprise connections | Connections abstract multiple IdP/user sources; OIDC/SAML/social federation | login-time profile sync, SCIM inbound provisioning, account linking | Organization/application roles and permissions outside the core connection model | `Connection` maps to neutral `IdentitySourceConnection`; multiple external identities can resolve to one application-local account/profile. |
| **PingOne** | Organization → environment → population; users, groups | Authoritative IdP can be set; SSO and external IdPs | source/target provisioning connections, rules, filters, attribute mapping | applications, grants/scopes, roles, sign-on policy | Very strong evidence for `AuthoritativeIdentitySource`; population/realm is a management partition, not a group and not an identity context. |
| **Keycloak** | Realm contains users, credentials, roles, groups; clients represent relying applications/services | Identity brokering delegates auth to IdPs; user federation connects external directories | local/external user management; sessions/tokens; identity linking | realm/client roles; client scopes; policies depending on extensions | Critical distinction: **user federation (identity store integration) ≠ identity brokering (authentication federation)**. Also confirms realm/client/session abstractions. |
| **ZITADEL** | Organization, human users, service accounts, projects | external IdPs + linked federated users; OIDC/SAML | invite/link/deactivate/reactivate/delete; session and auth-method lifecycle | project/org role assignments and admin roles | Confirms local account vs federated identity link and organization/project-scoped grants; machine accounts are distinct from human users. |
| **Ory** | Identity with schema/traits/credentials; Kratos identity/authentication separated from Keto authorization | OIDC/social integrations in identity flows; sessions after auth | registration, login, recovery, settings, session lifecycle | relation/permission model between subject and object in Keto | Supports modular separation of `Identity/Profile`, `Credential`, `Session`, and authorization relationship; useful for evaluating compositional architecture. |
| **authentik** | Users/groups and external Sources; Applications and Providers | Sources ingest/federate identity; Providers authenticate users for applications | LDAP/SCIM/social sources; provisioning/deprovisioning; flows/stages | policies bound to sources/apps/providers; application access | Strong anti-conflation: **Source ≠ Provider ≠ Application**. A source supplies/synchronizes identity, a provider performs application-facing authentication, and an application consumes it. |

## 2. Cross-platform recurring semantic layers

The operational benchmark repeatedly separates the following layers:

1. **Identity-bearing entity** — person, software workload, device, organization or other subject of identity.
2. **Account / directory representation** — a managed identity object/profile in a specific administrative domain.
3. **Identity source / authority** — the system authoritative for some account/profile/credential data.
4. **Federation connection / trust configuration** — relationship allowing authentication or assertions from an external authority.
5. **Provisioning** — creation, synchronization, update, disablement and removal of local/target account representations.
6. **Authentication and session** — an authentication event establishes a bounded session/security context.
7. **Authorization principal** — the identity representation evaluated for access.
8. **Access assignment / grant** — relationship binding a principal to permissions/role bundle in a scope/resource context.
9. **Permission / entitlement** — an allowed operation/capability; not equivalent to a user role label.
10. **Policy / condition** — rules and contextual predicates used to decide or constrain access.
11. **Resource / application/client** — target or participant consuming authentication/authorization services.
12. **Administrative partition** — tenant, realm, environment, population or organization boundary for identity objects/configuration.
13. **Identity linking** — relationship connecting multiple external/local account representations that refer to one subject/account experience.
14. **Attribute mapping / profile sourcing** — transformation/provenance rules governing how external attributes populate local profiles.
15. **Lifecycle state** — active, suspended, disabled, deprovisioned, deleted, expired or related account/session/access states.

## 3. High-priority anti-conflation rules

- **IAM Role / Permission Set / Role Binding ≠ UFO Role.** In cloud platforms these usually denote permission bundles, security identities or grant relationships.
- **User / Account / Profile ≠ IdentitySubject.** A user object is typically a platform-local representation of a subject, not the subject itself.
- **Principal ≠ Person.** A principal is an authorization-relevant identity representation and may be human, workload, service account or group/federated principal.
- **Tenant / Realm / Population ≠ IdentityContext.** These are administrative or isolation scopes; identity context describes the contextual scope of a digital identity and may cross or sit within such partitions.
- **Identity Source ≠ Identity Provider.** A source is authoritative for identity data; an IdP authenticates/asserts. One system may play both roles, but the functions differ.
- **User Federation ≠ Authentication Federation.** Directory synchronization/lookup and delegated authentication are independent mechanisms.
- **Provisioning ≠ Enrollment.** Provisioning creates/synchronizes a platform account representation; CM4DI Enrollment currently grounds subscriber/provider participation and must not absorb all account synchronization semantics.
- **Assignment / Grant ≠ Authorization Event.** Assignment establishes durable access relations; authorization evaluates access at runtime.
- **Session ≠ AuthenticationResult.** A result records the outcome of an event; a session is a temporally extended security context created after successful authentication.
- **Credential ≠ Token ≠ Temporary Cloud Credential.** Tokens and role/session credentials are protocol/operational artifacts and should map through explicit subtypes or profile artifacts rather than overload generic `Credential`.
- **Application Object ≠ Application Instance / Service Principal.** Entra supplies a concrete example of type/configuration versus tenant-local security representation.
- **Group ≠ Role ≠ Population.** Group is membership collection; platform role often means permission bundle; population is mutually exclusive management partition in PingOne.
- **Connection ≠ Identity Provider.** Auth0 connection is a configured relationship to a source, not the provider entity itself.
- **Source ≠ Provider.** authentik provides a direct operational example: Sources ingest identities; Providers authenticate users for applications.

## 4. Implications for existing CM4DI concepts

### `IdentityProvider`
Keep the concept, but narrow/clarify it as an **authentication/federation provider role** rather than a universal identity-source/provider superclass. Operational evidence strongly supports a separate `IdentitySource`/`AuthoritativeIdentitySource` abstraction.

### `DigitalIdentity`
Operational systems repeatedly materialize users/accounts/profiles/service principals. These should not automatically become `DigitalIdentity` subclasses. Gate B should decide whether `Account` is a distinct information/social object that **represents** an IdentitySubject and may instantiate/use a DigitalIdentity in a platform context.

### `Enrollment`
Do not overload with SCIM/JIT provisioning. A separate `Provisioning` process/event family is warranted at least in the Enterprise/Federated Profile.

### `Authorization`
Standards-wave candidates `Resource`, `Action`, `Decision` are strongly operationally confirmed. Enterprise IAM adds durable `AccessGrant/Assignment`, `Permission`, `PermissionBundle` and `Condition` semantics that sit around but are not identical to runtime Authorization.

### `AuthenticationResult`
Operational IAM strongly supports adding `Session` as a distinct post-authentication context with issue, expiry, refresh and revocation lifecycle.

### `Identifier` / `Claim` / `IdentityAttribute`
Attribute mappings and profile sources show the need to preserve provenance and source-of-authority information for values moved between directories and federation boundaries.

## 5. Saturation decision

The selected platforms cover hyperscale cloud IAM, workforce federation, CIAM, commercial identity platforms and mature open-source IAM. After Keycloak, ZITADEL, Ory and authentik, additional reviewed patterns increasingly repeat directory/source, broker/provider, tenant/realm, account/profile, session, assignment, provisioning and policy constructs. Therefore the issue is sufficiently saturated for Gate-B preparation without adding more vendors solely to increase count.

## 6. Boundary with Issue #6

This issue records enough non-human evidence to prevent a human-only Core, but detailed modeling of workload identity, service principals, managed identities, device identity and AI-agent identity is **deferred to Issue #6**. Enterprise findings here must not pre-empt that ontology analysis.

## 7. Source set

Curated evidence records are in `ENTERPRISE_IAM_EVIDENCE_REGISTRY.csv` (`CM4DI-EVID0046`–`CM4DI-EVID0070`). All retained product claims were drawn from current official vendor/project documentation; product marketing terminology was not used as ontology-admission evidence where technical documentation was available.