# Google Cloud Identity Ecosystem Semantic Benchmark — pass 1

Issue: #90. Evidence role: operational cloud IAM/federation/workload benchmark, not ontology authority.

## High-value semantic findings

### Google IAM gives a clean authorization triad
Google documents IAM access through `Principal + Role + Resource`, with roles as collections of permissions and policy bindings granting roles to principals on resources. This strongly supports CM4DI separation among `Principal`, `PermissionBundle`, `Permission`, `Resource` and `AccessGrant`.

### Role is not an ontological Role
Google IAM roles are named collections of permissions. A role grant to a principal on a resource is represented by a policy binding. Therefore:
`Role -> PermissionBundle`, while `RoleBinding -> AccessGrant`.
Neither should be modeled as a UFO contextual Role solely because Google calls it a role.

### Effective access is richer than one grant
Allow policies can inherit through resource hierarchy; deny policies can override grants; principal access boundary policies restrict eligible resources; conditions make bindings context-sensitive. This confirms that CM4DI should keep a neutral authorization kernel and represent effective-access composition through policies/constraints/evaluation rather than exploding Core classes.

### ServiceAccount is both resource and principal in Google IAM
Google explicitly describes service accounts as non-human users and as both a **resource** and a **principal**. Ontologically, this is a useful demonstration of contextual role-playing: the same managed account artifact can be protected/administered as a Resource while also playing Principal in authorization. It still must not be equated with the executing Workload.

### Workforce Federation and Workload Federation are materially different
Google separates:
- Workforce Identity Federation for employees, vendors and partners;
- Workload Identity Federation for external workloads.

Both use pools/providers and attribute mapping, but have different intended identity populations and security/lifecycle patterns. This strongly reinforces CM4DI’s separation of generic Federation from the Workload Identity domain.

### Federation provider configuration is not the external IdP
A workforce/workload pool provider is a configuration object that maps assertions from an external OIDC/SAML identity provider into Google attributes and principals. This maps to `FederationConnection` plus `AttributeMapping`; the actual external IdP may separately play an `IdentitySource` role.

### `google.subject` is a scoped normalized Identifier, not identity equality
Google best practices recommend a one-to-one mapping between external identities and `google.subject` for auditability. This is strong evidence for scoped identifier semantics. The mapped subject is a reference derived from an external assertion and must not be treated as `owl:sameAs` with the external identity object.

### PrincipalSet is a set-selection mechanism, not automatically a Group
Google `principalSet` identifiers can select principals by external group or mapped attribute. This matters because a dynamic attribute-selected principal set is not necessarily a persistent `AccessGroup` entity. It is better treated as an authorization selection pattern unless a real managed group exists.

### Workload federation exposes two valid authority paths
An external workload may:
1. receive **direct resource access** as a federated principal; or
2. receive permission to **impersonate a service account**, then obtain a short-lived access token.

This clearly separates external Workload/Principal, ServiceAccount representation, Delegation/impersonation, TokenExchange and TemporaryCredential. It is a strong anti-conflation benchmark.

### Provider disable state reveals layered lifecycle semantics
A disabled workforce provider cannot be used for new token exchange, but already-issued tokens can remain valid. Thus connection/provider lifecycle is distinct from credential/session lifecycle. A single generic “disabled identity” status would be semantically wrong.

### Google Privileged Access Manager is a new adjacency signal
The current IAM overview explicitly includes Privileged Access Manager for temporary, auditable access with request/justification/approval. This reinforces the Discovery Radar decision to treat PAM/JIT authority activation as a distinct adjacent research/benchmark area rather than forcing it into existing static AccessGrant semantics.

## Relation discoveries
1. Principal **is granted** Role **on** Resource → AccessGrant.
2. Role **contains** Permissions → PermissionBundle composition.
3. AllowPolicy **contains** role bindings and **is attached to** Resource.
4. Resource **inherits** policy effects from parent container resources.
5. Condition **qualifies** role binding/policy.
6. ServiceAccount **plays** Principal and may separately be Resource.
7. Workforce/Workload Pool **contains** Provider configurations.
8. Provider **maps** external claims to normalized subject/group/custom attributes.
9. mapped subject **identifies/references** federated principal.
10. external workload credential **is exchanged by** STS into federated token.
11. federated principal **may impersonate** ServiceAccount after access grant.
12. impersonation **issues** short-lived credential/token.
13. provider state **controls future token exchanges** independently of previously issued token validity.
14. PAM entitlement/request **may create temporary AccessGrant** after approval.

## Lifecycle/constraint discoveries
- provider create/enable/disable/expire;
- pool/provider attribute-map updates;
- short-lived STS token issue/expiry;
- service-account impersonation grant/revoke;
- service-account key/credential lifecycle where keys are used;
- allow/deny/boundary policy changes;
- conditional grant activation based on request/resource/time;
- PAM request/approval/activation/expiry.

## Candidate semantic deltas for #66
1. generic FederationConnection status/lifecycle pattern.
2. resource-scope/hierarchy relation relevant to authorization, likely outside identity Core.
3. distinguish managed `AccessGroup` from dynamically selected `PrincipalSet`.
4. authority activation/temporary grant event across Google PAM/AWS role assumption/Entra PIM.
5. review `TemporaryCredential` module ownership because it is cross-paradigm.
6. explicit impersonation/delegation relation from federated principal to service-account principal.
7. attribute-mapping provenance/uniqueness constraints should appear in SHACL/evaluation.

## DDD verdict
No Domain or Bounded Context rename/split/merge is justified. Google strongly validates:
- Authorization as a separate Generic Subdomain;
- Federation as distinct from Identity Administration;
- Workload Identity as distinct from Workforce Federation;
- Identity Representation/Identifier semantics independent of vendor subject identifiers.

## New discovery opportunities
- Cross-cloud **Role/Permission/Grant** benchmark (AWS, Entra, Google).
- Cross-cloud **Workload Federation and Impersonation** benchmark.
- Cross-system **Temporary Authority Activation** pattern (Google PAM, AWS STS, Entra PIM, CyberArk/Teleport).
- **PrincipalSet vs AccessGroup** distinction for relationship/attribute-based authorization.
- Audit provenance of token exchange/impersonation may strengthen PROV-O alignment and evaluation scenarios.

## Remaining before closing #90
Cloud Identity directory lifecycle; Google Groups; workforce pool/provider full API state model; workload provider types; service-account credentials/impersonation APIs; Privileged Access Manager; deny/PAB policies; exact CQ mappings; final #66 disposition.
