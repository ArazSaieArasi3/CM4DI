# Cross-Cloud Identity Semantic Benchmark — AWS, Microsoft Entra, Google Cloud

Status: pass-1 synthesis. Sources: Issues #88, #89, #90. This is operational evidence, not ontology authority.

## Why this comparison matters
The same lexical labels (`role`, `principal`, `identity`, `application`, `account`, `policy`, `federation`) denote materially different objects and relations across cloud providers. CM4DI's value is therefore not a common glossary but a neutral ontology that separates identity-bearing entities, managed representations, contextual roles, authorization grants, policy artifacts, federation configurations and temporal sessions/credentials.

| Semantic concern | AWS | Microsoft Entra | Google Cloud | CM4DI interpretation |
|---|---|---|---|---|
| Authorization actor | IAM Principal; role-session principal | security principal: user/group/service principal/agent | Principal / principalSet | `Principal` roleMixin; implementation identity kind remains separate |
| Managed human representation | IAM User / Identity Center User | User directory object | Google/Cloud Identity account/federated workforce principal | `Account` + `UserProfile`, representing `IdentitySubject` |
| Non-human managed representation | IAM Role/service-linked role/service identities | ServicePrincipal; ManagedIdentity; AgentIdentity | ServiceAccount; federated workload principal | `ServiceAccount`, `ServicePrincipal`, `ManagedIdentity`, `AgentIdentity` plus contextual `Principal` |
| Application definition/registration | client/resource/application settings vary by service | ApplicationObject/AppRegistration | OAuth/client/service resource-specific registrations | `Application` != `ApplicationRegistration` != local principal representation |
| Local application security representation | assumed IAM role/session patterns | tenant-local ServicePrincipal | ServiceAccount or federated principal depending pattern | explicit representation/role mappings; no lexical equivalence |
| Role | assumable IAM Role with trust and permission policies | AppRole or DirectoryRole definition | collection of Permissions | primarily `PermissionBundle`; AWS assumption and Entra app semantics add relations/events |
| Grant/assignment | policies, group membership, Identity Center account assignment | AppRoleAssignment / RoleAssignment / OAuth2PermissionGrant | role binding in allow policy | `AccessGrant` plus policy/scope/delegation context |
| Permission | policy action/resource statement semantics | app permission/delegated permission/directory action | atomic IAM permission | `Permission`; source-specific bundle/statement model maps conservatively |
| Scope | resource ARN/account/session restrictions | tenant/app/directory/resource scope | resource hierarchy + conditional binding | Resource/scope relation and `AuthorizationContext`; no generic vendor scope class |
| Policy | identity/resource/trust/session/boundary/SCP policies | Conditional Access; role/app consent policies | allow/deny/PAB/conditions | `AccessPolicy` + `AccessCondition`; effective-permission composition evaluated outside minimal Core |
| Federation | SAML/OIDC/Identity Center/Cognito | external identities/enterprise apps/federation | Workforce/Workload Identity Federation | `Federation`, `FederationConnection`, `IdentityBroker`; separate from provisioning |
| Provisioning | SCIM/AD sync/Identity Center provisioning | SCIM/provisioning directory sync | Cloud Identity/SCIM and source sync patterns | `Provisioning` + `ProvisioningConnection`; never Federation by default |
| Temporary authority | STS AssumeRole session | delegated/app grants; PIM/JIT patterns | PAM temporary grants; STS/impersonation | candidate cross-provider AuthorityActivation/JIT pattern + `AccessGrant`/`Session` |
| Temporary credentials | STS credentials | access tokens/managed identity tokens/agent exchange | STS and service-account short-lived tokens | `TemporaryCredential`; module ownership should be cross-paradigm reviewed |
| Workload federation | roles, OIDC/SAML and Roles Anywhere patterns | workload identity/FIC + ServicePrincipal/ManagedIdentity | Workload Identity Pool + STS + direct or impersonated access | Workload Identity Domain with Federation and TokenExchange bridges |
| Agent identity | emerging AWS/service/workload patterns; no pass-1 first-class neutral agent object | first-class AgentIdentity service-principal subtype + Blueprint + Sponsor | current generic principals/service accounts; no pass-1 equivalent first-class agent object | Entra is strong evidence for AgentIdentity/AgentSponsor but cross-vendor convergence still required |
| Identity equality/linking | no generic sameAs; role sessions are separate principals | application object != service principal; agent != blueprint | google.subject mapping/audit identifier != external entity | representations/correlation must never default to `owl:sameAs` |

## Cross-cloud relation patterns

### Representation relation
Microsoft provides the clearest explicit pattern: one ApplicationObject may have multiple tenant-local ServicePrincipals. This supports a generic **representation/local-security-instance** relation rather than subclass/equality.

### Assignment relation
All three ecosystems separate a permission/role definition from the principal-to-scope assignment:
- AWS PermissionSet → AccountAssignment;
- Entra RoleDefinition/AppRole → RoleAssignment/AppRoleAssignment;
- Google Role → Policy RoleBinding.

This is strong convergence for `PermissionBundle/Permission != AccessGrant`.

### Authority activation relation
AWS `AssumeRole`, Google Privileged Access Manager/service-account impersonation and Entra PIM/agent on-behalf-of flows indicate a broader temporal pattern: an existing eligibility/grant is **activated or exercised** to create a bounded session/principal/credential. This may justify a profile-level event/relator after deeper cross-source review.

### Federation identity normalization
Google's `google.subject`, Entra external identities/FIC mappings and AWS external federation all require source-to-local identifier/claim mapping. This supports `AttributeMapping`, scoped `Identifier`, provenance and explicit source/binding semantics.

### Effective authorization
All providers compute effective access from multiple policies, hierarchy/scope and conditions. Therefore CM4DI should not attempt to encode vendor-specific policy-calculation algorithms in Core. The journal should demonstrate semantic bridging and CQ evaluation rather than pretending one universal policy language.

## Candidate cross-cloud CQs
1. Can the ontology distinguish a permission bundle from its assignment and the runtime authorization result?
2. Can the same managed object play Principal and Resource roles without type conflation?
3. Can an application definition be distinguished from a tenant-local security representation?
4. Can a federated workload act directly or through service-account impersonation without equating workload, account and credential?
5. Can temporary credentials and sessions be represented independently from the durable grant that enabled them?
6. Can policy conditions and scope constrain an AccessGrant without redefining the identity subject?
7. Can account/representation correlation remain weaker than identity equality?
8. Can an agent identity have a sponsor, delegated authority and a separate software-agent bearer?

## DDD result
Across all three providers, no evidence currently justifies changing the 15 canonical Domain names or 13 Bounded Contexts. The strongest result is positive validation of separation among **Identity Administration**, **Federation**, **Authentication**, **Authorization**, **Workload Identity** and **Agent Identity**. The naming rule remains intact: no canonical Domain name uses `and`, `&`, or a slash-composed semantic center.

## Reconciliation candidates for #66
- Application↔local service-principal representation relation.
- Scoped `authoritativeFor` relation for identity-information sources.
- Account/FederationConnection/AccessGrant/Session lifecycle patterns.
- Authority activation/JIT event pattern.
- TemporaryCredential module ownership.
- explicit impersonation/on-behalf-of relation layered over Delegation.
- Agent blueprint/sponsor/lifecycle relation patterns.
- resource-scope hierarchy and effective-policy constraints allocated to profile/SHACL/evaluation rather than Core.
