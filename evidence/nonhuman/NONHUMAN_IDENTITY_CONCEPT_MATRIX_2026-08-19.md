# CM4DI Journal V2 — Non-Human Identity Concept Matrix

**Review date:** 2026-08-19  
**Scope:** Issue #6 / roadmap D15–D16  
**Method:** bounded review of authoritative workload-identity, device-identity, SPIFFE/SPIRE and AI-agent identity sources. Product terms are evidence, not ontology classes.

## 1. Cross-ecosystem matrix

| Ecosystem | Identity-bearing target | Identity representation / account | Identifier | Credential / proof | Binding / attestation | Authorization context | Main CM4DI implication |
|---|---|---|---|---|---|---|---|
| Microsoft Entra Workload ID | application/service/software workload | application object, service principal, managed identity | object IDs / app IDs | secret, certificate, federated credential, token | app registration / federated trust | service-principal permissions, Conditional Access | Workload ≠ service principal ≠ credential. Application definition and tenant-local principal are distinct. |
| Google Workload Identity Federation | external workload | federated principal; optional service-account impersonation | external subject + pool/provider namespace | external OIDC/SAML/X.509 credential → short-lived token | provider config + attribute mapping | direct principal grants or service-account impersonation | Federated workload identity can authorize directly without creating a durable service account. |
| Kubernetes | workload/process in Pod | ServiceAccount object | namespaced service-account identity | projected short-lived token | Pod assigned to ServiceAccount | RBAC RoleBinding | ServiceAccount is a non-human account used by workloads; it is not the Pod/process itself. |
| AWS EKS Pod Identity | application workload in Pod | Kubernetes ServiceAccount + PodIdentityAssociation + IAM role | cluster/namespace/service-account coordinates | pod identity token → temporary AWS credentials | association maps ServiceAccount to IAM role | IAM policies/role session | A workload may traverse several identity/access representations; none should be collapsed into the workload itself. |
| AWS IAM Roles Anywhere | server/container/application outside AWS | no required durable AWS user identity; IAM role assumed at runtime | certificate subject + AWS role/session identifiers | X.509 certificate → temporary credentials | external CA registered as trust anchor | assumed IAM role session | Workload identity can be externally proven and exchanged for a temporary security context. |
| SPIFFE/SPIRE | running workload/process/service | no generic account object required | SPIFFE ID | SVID (X.509/JWT/WIT) | workload attestation binds runtime evidence to identity | downstream policy can use SPIFFE ID | Identifier, verifiable identity document, workload, attestation and trust domain are explicitly separate. |
| Microsoft Entra device identity | physical/virtual device | directory Device object | device/object identifiers | device registration certificate/tokens | registration/join establishes directory representation | device-based Conditional Access | Device ≠ DeviceIdentityRecord ≠ device credential/authenticator. |
| AWS IoT | physical IoT device | Thing registry representation | thing name/ARN | X.509 certificate or Cognito identity principal | principal attached to Thing | IoT policies | Physical device, registry record and authenticating principal/credential are separate. |
| Microsoft Entra Agent ID | autonomous AI agent | Agent Identity; optionally paired agent user account | agent identity/object identifier | Entra access tokens | creation/blueprint; sponsor/owner governance | autonomous rights or delegated user rights | Agent ≠ agent identity account ≠ human sponsor/user; delegation requires actor/subject distinction. |
| AWS AgentCore Identity | AI agent / automated workload | workload identity in agent identity directory | workload identity ARN | workload access token; external credentials via providers | identity associated with agent deployment | direct and third-party tool/service access | Agent identity can be a specialized workload identity and persist independently of deployment/credential scheme. |

## 2. Recommended ontological separation

A defensible Gate-B direction is **not** a flat taxonomy called `MachineIdentity`. Instead separate at least five layers:

1. **Identity-bearing entity** — the entity whose identity matters: person, organization, device, software agent, running workload/process, possibly other artifacts depending on UFO analysis.
2. **Operational entity / execution** — application definition, deployed service, process, Pod, workflow/job, AI-agent instance. These have different identity criteria and lifecycles.
3. **Digital identity / account / principal representation** — service account, service principal, managed identity, agent identity, device record or federated principal are representations/roles in an identity system; they are not automatically subtypes of the entity they represent.
4. **Identifier** — SPIFFE ID, service-account subject, device ID, application/client ID, workload identity pool subject and similar identifiers.
5. **Credential / proof / security context** — SVID, certificate, projected token, OIDC assertion, temporary access token, role session and other artifacts used to prove identity or exercise authorized access.

## 3. Critical identity criteria

### Software application vs running workload
An application can be a durable software artifact/definition while a workload is an executing deployment/process. Microsoft explicitly separates application object from tenant-local service principal; SPIFFE focuses on running workloads; Kubernetes identities are commonly assigned to Pods/processes. Do not make `Application`, `Service`, `Workload` and `Process` synonyms.

### Workload vs workload identity
A workload performs computation. A workload identity is a digital identity/representation that enables the workload to authenticate and be authorized. One workload may receive different identities in different environments; an identity may also represent a class of workload instances depending on platform design.

### Service account vs service principal vs managed identity
These are platform-specific representation patterns. `ServiceAccount` is best treated as an account/profile pattern; `ServicePrincipal` as a tenant-local security-principal/application-instance pattern; `ManagedIdentity` as a credential-managed workload identity pattern. Gate B should seek neutral abstractions rather than a vendor taxonomy in Core.

### Device vs authenticator
A device may be an identity subject in its own right and have a directory/registry identity. A device can also host or function as an authenticator for a human or workload. These are different roles. A phone enrolled as a managed device is not ontologically identical to a FIDO authenticator simply because the same hardware can play both roles.

### AI agent vs application/workload
Current authoritative platforms provide evidence that AI agents are software entities with goal-directed/autonomous behavior, dynamic lifecycle and delegated/autonomous access patterns. This supports an `Agent` profile distinction, but evidence is too product-emergent to force an AI-specific class into Core before academic and UFO analysis.

## 4. High-confidence cross-source patterns

- **Non-human identity-bearing entities are real scope requirements**, not edge cases.
- **Principal is a contextual authorization role**, not a synonym for person/entity.
- **Account/identity representation is distinct from represented subject/entity.**
- **Credential exchange and temporary credentials are lifecycle artifacts, not identity replacement.**
- **Attestation establishes evidence about a workload/node/device and can ground identity issuance/binding.**
- **Trust domain is a security/identity namespace, not the same as a government Trust Framework or CM4DI IdentityContext.**
- **Federation for workloads can mean trust/credential exchange across non-human namespaces; it should map to a generic federation pattern while retaining profile semantics.**
- **Delegation / on-behalf-of is especially important for agents and validates the earlier Actor-versus-Subject candidate from token-exchange standards.**
- **Ephemerality is a lifecycle characteristic, not a new ontological kind.** A dynamically created agent or workflow identity may be short-lived while its underlying agent/application pattern is durable.

## 5. Profile architecture implication

The existing proposed `Machine/Workload/Device/Agent Profile` remains justified, but it should be internally organized into four views rather than one flat list:

- **Workload Identity View** — workload, workload identity, workload account/principal, federation, temporary credentials, runtime binding.
- **SPIFFE/Attestation View** — SPIFFE ID, SVID, trust domain/bundle, workload attestation, workload API and cross-domain federation mappings.
- **Device Identity View** — device, device identity record, registration/join, device credential, device state/trust and device-as-authenticator relation.
- **AI Agent Identity View** — agent, agent identity, sponsor/owner, autonomous access, delegated access, agent lifecycle and tool/service access.

These views can share neutral Core primitives without implying that device, workload and AI agent have the same identity criteria.

## 6. Gate-B recommendation

### Strong Core-level questions
- Should `IdentitySubject` be explicitly generalized to identity-bearing human and non-human entities rather than relying on ambiguous `Party` assumptions?
- Should CM4DI introduce a neutral `Principal` role for authorization contexts?
- Should `DigitalIdentity` explicitly represent identities of devices/software/workloads as well as persons/organizations?
- Should generic `IdentityBinding` / `Attestation` / `Evidence` patterns connect entity, identity representation and credential issuance?
- Should delegation be a reusable Core relation/relator because both token exchange and agent identity require actor-versus-subject semantics?

### Profile-first candidates
- Workload, ServiceAccount, ServicePrincipal, ManagedIdentity, WorkloadIdentityPool, SPIFFEID/SVID, TrustDomain, DeviceIdentityRecord, AgentIdentity, AgentSponsor, AgentBlueprint, autonomous-agent access and workload-specific credential mechanisms.

### Mapping-only candidates
- AWS IAM role/Pod Identity Association, Entra-specific object types, Google workload pool/provider, Kubernetes namespaced ServiceAccount mechanics, specific AgentCore or Agent ID product objects.

No candidate is admitted to canonical CM4DI until Gate B and subsequent UFO/OntoUML analysis.