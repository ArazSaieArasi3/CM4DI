# P03 — Technical Identity Profile

**Legacy label:** Machine / Workload / Device / Agent  
**DDD status:** Cross-domain integration Profile. `Technical Identity` is a profile/grouping view, not a monolithic DDD Domain.

## Purpose
Represent technical and non-human identity scenarios without introducing a misleading `MachineIdentity` superclass or forcing Workload Identity, Device Identity and Agent Identity into one problem-space model.

## Domain composition
P03 composes Identity Representation, Identity Evidence, Credential Management, Authentication, Authorization, Identity Administration, Workload Identity, Device Identity, Agent Identity and Trust Governance.

## Domain reuse
- `Workload`, `Device` and `SoftwareAgent`/`AIAgent` belong to three separate DDD subdomains and Bounded Contexts.
- All may play `IdentitySubject`, `Party`, `Principal` and context-specific roles without sharing a fabricated MachineIdentity kind.
- `ServiceAccount`, `ServicePrincipal` and `ManagedIdentity` belong primarily to Workload Identity and link explicitly to Identity Administration and Authorization.
- SPIFFE ID maps to Identity Representation `Identifier`; SVID reuses Credential Management and may play Identity Evidence roles.
- Node/Workload Attestation consumes Identity Evidence/IdentityBinding.
- Device may independently play IdentitySubject and Authenticator; these are separate role occurrences.
- Agent delegated access consumes Authorization `Delegation`; autonomous rights consume `AccessGrant`.

## Profile concepts
P03 contributes 18 governed concepts distributed across Workload Identity, Device Identity and Agent Identity. Primary assignments are canonical in `../ddd/CONCEPT_DOMAIN_ASSIGNMENT_v2.csv`.

## Representative external alignments
- SPIFFE/SPIRE: SPIFFE ID -> Identifier; SVID -> Workload Identity/Credential; TrustDomain/TrustBundle remain technical trust constructs; attestation grounds Identity Evidence.
- Kubernetes: ServiceAccount and projected credentials are Workload Identity constructs.
- Microsoft Entra: ServicePrincipal and ManagedIdentity are Workload Identity; Device object maps to DeviceIdentityRecord; AgentIdentity/AgentSponsor map to Agent Identity.
- Google Workload Identity Federation: Workload and ServiceAccount semantics compose Workload Identity, Federation and Authorization.
- AWS workload/agent patterns: temporary credentials, principals, grants and agent identity are explicitly cross-domain.

## Anti-conflation invariants
`Workload != WorkloadIdentity`; `Workload != ServiceAccount`; `ServiceAccount != ServicePrincipal`; `ServicePrincipal != Application`; `Device != DeviceIdentityRecord`; `Device != Authenticator`; `SPIFFE ID != SVID`; `TrustDomain != IdentityContext`; `TrustDomain != TrustFramework`; `Attestation != Authentication`; `AgentIdentity != AIAgent`; `Sponsor != Delegator` by default.

## Minimum scenarios
1. Workload identity composes Identity Representation + Identity Evidence + Credential Management + Workload Identity + Authorization.
2. Device identity composes Identity Representation + Device Identity + Authentication/Authorization roles as required.
3. Agent identity composes Identity Representation + Agent Identity + Authorization + Trust Governance accountability where needed.

## Wave-7 formalization expectation
Formal packaging MUST follow the DDD Context Map. Workload Identity, Device Identity and Agent Identity may become separate formal modules or a controlled technical-identity aggregate only if dependency analysis justifies it. P03 itself is not automatically an OWL module.