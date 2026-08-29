# IAM, SSO and Cloud Identity Benchmark Matrix

Status: **initial operational benchmark — official-source seeded, exhaustive product mining pending Issue #72**.

## Purpose
This matrix compares representative IAM/CIAM/SSO/cloud-identity products as operational evidence. It is not a market-ranking table and does not treat product vocabulary as ontology authority.

## Benchmark overview

| Platform | Administrative boundary | Managed identity representations | Federation / SSO | Authorization / assignment | Non-human identity | High-value CM4DI lesson |
|---|---|---|---|---|---|---|
| AWS IAM | AWS account | IAM user, IAM role | External IdP federation and role assumption | Policies, permissions, conditions | Strong through roles | `Principal`, `Permission`, `PermissionBundle` and durable access assignment remain distinct. |
| AWS IAM Identity Center | AWS Organization/account instance | User, group, permission-set assignment | Workforce SSO and external IdP | Permission sets and account assignments | Indirect through IAM roles | `PermissionSet` is operational bundling; assignment is closer to `AccessGrant` than runtime authorization result. |
| Amazon Cognito | User Pool / Identity Pool | User, app client, federated identity | OIDC/SAML/social identity providers | Groups/scopes plus AWS credential integration | Application identities adjacent | A user pool is an implementation of IdentityStore/AdministrativeDomain, not `IdentityContext`. |
| Microsoft Entra ID | Tenant / directory | User, group, application object, service principal | OIDC/OAuth2/SAML, B2B | App roles, RBAC, permissions, Conditional Access | Strong | Application object and tenant-local service principal are not the same entity. |
| Microsoft Managed Identities | Azure tenant/resource scope | Managed identity represented by special service-principal semantics | Token service rather than end-user SSO | Azure RBAC assignments | Core focus | Identity lifecycle can be platform-managed and can be tied to or independent of resource lifecycle. |
| Google Cloud IAM | Organization/folder/project/resource | Principal, service account | External identity integration | Roles, permissions, allow policies | Strong | Google roles are permission bundles, not UFO roles. |
| Google Workforce Identity Federation | Workforce pool | Federated workforce subject/group attributes | OIDC/SAML SSO | IAM allow policies with mapped attributes | Human workforce | Strong evidence that federation can be **sync-less**, hence `Federation != Provisioning`. |
| Google Workload Identity Federation | Workload pool | External workload subject, service-account target | Federated token exchange | IAM binding/impersonation | Core focus | `Workload`, external identity, `ServiceAccount`, `TemporaryCredential` and `TokenExchange` require separate semantics. |
| Okta | Okta org | User, profile, app user, group | OIDC/SAML/social, IdP routing | Policies, groups, assignments | Current service-account support exists | Universal Directory strongly supports `IdentityStore`, `UserProfile`, `IdentitySource`, `AttributeMapping`; account linking is not identity equality. |
| Auth0 | Tenant | User, organization/member, application | Enterprise/social/database/passwordless connections | Roles/permissions | M2M applications | A `Connection` is a source/federation configuration pattern rather than a Core semantic object. |
| Keycloak | Realm | User, group, client, role | OIDC/SAML broker, social login | Realm/client roles, mappings, authorization services | Service accounts | `Realm != IdentityContext`; `Client` is closer to ApplicationRegistration; user federation is not Enrollment. |
| ZITADEL | Instance / Organization | User, Service Account, Project, Application | External IdP, OIDC/SAML, social login, account linking | Roles and role assignments | Strong | Organization/Project are operational boundaries; RoleAssignment is durable assignment; federated account linking reinforces `linkedAccount`. |
| Ory Kratos + Hydra | Deployment/project | Identity/schema/session plus OAuth client | OAuth2/OIDC through Hydra and login integration | OAuth2 scopes/consent plus external policy | Machine clients | Splitting identity lifecycle (Kratos) from authorization server (Hydra) supports bounded-context separation. |
| authentik | Instance/tenant | User, group, source, provider, application | OIDC/SAML/LDAP/proxy/federation | Policies/bindings | Some service/application patterns | Source, Provider, Flow and Stage need an Anticorruption Layer, not direct Core copying. |
| PingOne | Environment/organization | User/population/application/connection | Enterprise federation and SSO | Policy/role/entitlement features by product | Product-dependent | `Population` and `Environment` are operational boundaries, not identity contexts. |
| Dex | Deployment/connectors | Connector and claim-level subject view | Focused OIDC federation broker | Minimal downstream authorization | Limited | Useful minimal case showing broker/connector semantics without full identity administration. |

## Official-source anchors used in the seed pass

- AWS IAM identities: https://docs.aws.amazon.com/IAM/latest/UserGuide/introduction_identity-management.html
- AWS IAM policies and permissions: https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html
- AWS IAM Identity Center permission sets: https://docs.aws.amazon.com/singlesignon/latest/userguide/permissionsetsconcept.html
- Microsoft Entra overview: https://learn.microsoft.com/en-us/entra/fundamentals/what-is-entra
- Microsoft Entra application/service principals: https://learn.microsoft.com/en-us/entra/identity-platform/app-objects-and-service-principals
- Microsoft Managed Identities: https://learn.microsoft.com/en-us/entra/identity/managed-identities-azure-resources/overview-for-developers
- Microsoft Entra External ID: https://learn.microsoft.com/en-us/entra/external-id/external-identities-overview
- Google Workforce Identity Federation: https://docs.cloud.google.com/iam/docs/workforce-identity-federation
- Google Workload Identity Federation: https://docs.cloud.google.com/iam/docs/workload-identity-federation
- Okta Universal Directory: https://developer.okta.com/docs/concepts/universal-directory/
- Okta external Identity Providers: https://developer.okta.com/docs/concepts/identity-providers/
- Auth0 Identity Providers: https://auth0.com/docs/authenticate/identity-providers
- Keycloak Server Administration Guide: https://www.keycloak.org/docs/latest/server_admin/
- ZITADEL Organizations: https://zitadel.com/docs/guides/manage/console/organizations-overview
- ZITADEL Users and Service Accounts: https://zitadel.com/docs/guides/manage/console/users-overview
- ZITADEL roles/assignments: https://zitadel.com/docs/guides/manage/console/roles

## Cross-product semantic conclusions

### Identity storage and representation
Across products, the managed object usually called `User` is a platform record/account/profile, not the real-world person. CM4DI therefore keeps `IdentitySubject`, `DigitalIdentity`, `Account` and `UserProfile` distinct.

### Administrative boundary versus semantic context
AWS Account/Organization, Entra Tenant, Okta Org, Keycloak Realm, ZITADEL Organization and PingOne Environment are administration/security boundaries. They are not automatically equivalent to `IdentityContext`.

### Federation versus synchronization
Google Workforce Identity Federation is especially important because it explicitly avoids storing synchronized Google user accounts. This supports the current DDD split between `Federation` and `Identity Administration` and the anti-conflation rule `Federation != Provisioning`.

### Role vocabulary collision
AWS Role, Google Role, ZITADEL project role, Keycloak role and Entra role are not one ontological category. In CM4DI they normally map to a mixture of `Principal`, `PermissionBundle`, `Permission`, `AccessGrant` or contextual organization roles depending on use.

### Non-human identity
AWS roles, Entra service principals/managed identities, Google service accounts/WIF, ZITADEL service accounts and SPIFFE/SPIRE all confirm that non-human identity is not exceptional. The existing separation of Workload Identity from human account administration remains justified.

### Account linking
Okta and ZITADEL provide concrete operational account-linking behavior. These support a controlled co-reference/correlation relation but do not justify `owl:sameAs` between local accounts, external identities or identity subjects.

## Remaining exhaustive work
Issue #72 will expand source-level coverage for lifecycle, audit/governance, APIs, CIAM, identity stores, sessions, policy structures and current product changes. The final product matrix will also feed Gate-D scenario selection and the ontology-relational/service architecture crosswalk in Issue #76.