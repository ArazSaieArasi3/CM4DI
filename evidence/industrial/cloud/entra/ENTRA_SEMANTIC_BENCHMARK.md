# Microsoft Entra Identity Ecosystem Semantic Benchmark — pass 1

Issue: #89. Evidence role: operational cloud/enterprise IAM and emerging agent-identity evidence, not ontology authority.

## High-value semantic findings

### Application and ServicePrincipal are explicitly different
Microsoft documents an application object as the application definition/home-tenant record and a service principal as its local representation/application instance in a tenant. A multitenant application can therefore have one application object and multiple service-principal objects across tenants.

This is unusually strong evidence for a representational distinction that CM4DI must preserve:
- `Application` / `ApplicationRegistration` describe the application and registration semantics;
- `ServicePrincipal` is a tenant-local authorization/security representation playing `Principal`;
- representation is not ontological identity equality.

### ManagedIdentity is a specialized platform-managed service-principal pattern
Managed identities are represented through service-principal infrastructure while their credential lifecycle is platform managed. This reinforces `ManagedIdentity` as a Workload Identity extension and validates the anti-conflation rule `ManagedIdentity != ServicePrincipal != Application != Workload`, even though the implementation uses service-principal objects.

### Role definitions and assignments validate PermissionBundle versus AccessGrant
Microsoft Entra role assignments explicitly link a security principal to a role definition at a scope. App roles can be assigned to users, groups or service principals. This strongly supports:
`Permission/PermissionBundle != AccessGrant != Principal`, and scope must be explicit.

### Delegated and application permissions are semantically distinct
Application permissions are exercised app-only by service principals. Delegated permissions are exercised by an application in the context of a signed-in user and involve consent/delegation semantics. This reinforces `Delegation`, durable grants/consent records and contextual `Principal` rather than one generic permission-assignment pattern.

### Conditional Access is policy/context infrastructure
Conditional Access targets principals/resources and evaluates contextual signals such as device, risk and network before enforcing controls. This maps naturally to `AccessPolicy`, `AccessCondition`, `AuthorizationContext` and runtime authorization rather than a new identity class.

## Major new finding: Microsoft Entra Agent ID materially strengthens Agent Identity
Current Microsoft Entra Agent ID documentation introduces:
- **agent identity blueprint**;
- tenant-local **agent identity blueprint principal**;
- **agent identities** as a distinct service-principal subtype;
- one blueprint to many agent identities through a `ParentID` relation;
- assigned **sponsor**;
- direct and inherited application/delegated permissions;
- blueprint-mediated token exchange/impersonation on behalf of each agent;
- distinct audit/sign-in identity for each agent;
- agent-specific Conditional Access for autonomous and on-behalf-of scenarios.

This is stronger operational evidence than the initial generic AI-agent material used in Wave 6. It validates existing `AgentIdentity` and `AgentSponsor` concepts and reveals several relation/lifecycle patterns that require reconciliation before formal freeze.

### AgentIdentity is not the software agent itself
Entra Agent ID treats the directory/security identity as an identity object/service principal. The software/AI agent remains a distinct executing entity. This supports:
`AIAgent/SoftwareAgent != AgentIdentity != ServicePrincipal representation`, with role-playing relations between them.

### Blueprint-agent relation is not specialization
An agent identity inherits protocol properties and potentially delegated permission baseline from a parent blueprint. This is a template/provenance/configuration relationship, not a class-subclass relationship. OWL subclassing would be incorrect.

### Agent impersonation is not identity equality
The blueprint obtains tokens on behalf of the agent identity, while logs/tokens identify the agent as acting client. This is an excellent real-world case for separating:
- technical token exchange;
- delegated/on-behalf-of authority;
- acting Principal;
- credential source;
- software actor;
- identity representation.

## Relation discoveries
1. ApplicationObject **is represented by / instantiated as** ServicePrincipal in tenant.
2. ServicePrincipal **plays** Principal.
3. ManagedIdentity **uses** provider-managed ServicePrincipal representation.
4. security principal **assigned** role definition at scope → AccessGrant pattern.
5. resource application **defines** AppRole/permission.
6. client service principal **receives** application permission/app-role assignment.
7. delegated grant **authorizes client on behalf of user** → Delegation/AccessGrant pattern.
8. Conditional Access policy **targets** principal/resource and **evaluates** conditions.
9. AgentIdentityBlueprint **has many** AgentIdentity instances.
10. AgentIdentity **has/depends on** AgentSponsor governance relationship.
11. AgentIdentity **inherits** protocol properties/optional delegated permission baseline from blueprint.
12. Blueprint principal **creates/manages** AgentIdentity lifecycle.
13. Blueprint **obtains token on behalf of** AgentIdentity via token exchange/impersonation.
14. AgentIdentity **appears as acting client** in audit/sign-in evidence.

## Lifecycle discoveries
- application registration → tenant consent → service-principal creation;
- service-principal enable/disable/delete and assignment lifecycle;
- managed-identity create/credential-management/delete controlled by platform;
- role assignment create/remove;
- consent/grant create/revoke;
- device register/join/compliance/risk changes;
- agent blueprint instantiate/manage;
- agent identity create/permission assignment/sponsor governance/suspend-delete lifecycle;
- agent token exchange and audit event lifecycle.

## Candidate semantic deltas for #66
1. explicit `representsApplication` relation between Application and ServicePrincipal/local representation.
2. agent **Blueprint** concept/pattern may be profile-specific but materially cross-implementation if Auth0/Ping/Descope reveal equivalents.
3. `blueprintManagesAgentIdentity` / parent-template relation.
4. `sponsoredBy` relation from AgentIdentity/Agent to AgentSponsor should be explicit if not already governed.
5. agent token exchange/on-behalf-of pattern should be mapped to Delegation and TokenExchange without identity conflation.
6. permission inheritance from blueprint should remain authorization configuration, not ontology specialization.
7. AgentIdentity lifecycle/status deserves a cross-product comparison before deciding a new mode/event.

## DDD verdict
No canonical Domain rename/split/merge is justified. The existing Agent Identity Domain is strongly validated and now looks more strategically important. Agent-specific Conditional Access still belongs in Authorization, not a new `Agent Authorization` Domain.

## Research and product opportunities
- Agent Identity could become one of the strongest journal-v2 novelty differentiators if grounded across Entra, Auth0, Ping, Descope and emerging standards rather than one vendor.
- A reusable **Agent Identity Governance Bridge** can connect AgentIdentity, AgentSponsor, Delegation, AccessGrant, Credential and audit/provenance semantics.
- The application-object/service-principal pattern is a powerful benchmark for the more general representation-vs-subject distinction.

## Remaining before closing #89
External ID; device identity; workload identity federation/FIC; Conditional Access service-principal details; PIM/JIT role activation; app-consent object model; Graph/API schemas; agent lifecycle/preview-status tracking; exact CQ mapping; #66 disposition.
