# P03 — Machine / Workload / Device / Agent Profile

## Purpose
Represent non-human identity subjects and their operational identity representations without introducing a misleading `MachineIdentity` superclass.

## Core reuse
- `Workload`, `Device` and `SoftwareAgent` are profile/domain kinds that may play Core `IdentitySubject`, `Party`, `Principal` and, when appropriate, `Authenticator` roles.
- `ServiceAccount`, `ServicePrincipal` and `ManagedIdentity` are representation/principal patterns, not synonyms for workload or software agent.
- SPIFFE ID maps to Core `Identifier`; SVID specializes/maps to Core `Credential` and can play Core `Evidence`/`Proof` roles.
- Node/Workload Attestation produces evidence grounding Core `IdentityBinding` and `AssuranceAssessment` patterns.
- Agent delegated access reuses Core `Delegation`; autonomous access reuses `AccessGrant`.

## Profile concepts
P03 contributes 18 governed concepts: Workload, RuntimeInstance, ServiceAccount, ServicePrincipal, ManagedIdentity, Device, DeviceIdentityRecord, NodeAttestation, WorkloadAttestation, TrustDomain, TrustBundle, SVID, TemporaryCredential, TokenExchange, SoftwareAgent, AIAgent, AgentIdentity and AgentSponsor.

## Representative external alignments
- SPIFFE/SPIRE: SPIFFE ID -> Core `Identifier`; SVID -> P03 `SVID`/Core `Credential`; Trust Domain -> P03 `TrustDomain`; Trust Bundle -> P03 `TrustBundle`; Workload/Node Attestation -> P03 events grounded in Core Evidence/Binding.
- Kubernetes: ServiceAccount -> P03 `ServiceAccount`; projected service-account token -> `TemporaryCredential`; Pod/process/job -> Workload/RuntimeInstance depending granularity.
- Microsoft Entra: Service Principal -> P03 `ServicePrincipal`; Managed Identity -> P03 `ManagedIdentity`; Device object -> `DeviceIdentityRecord`; Agent Identity -> `AgentIdentity`; sponsor -> `AgentSponsor`.
- Google Workload Identity Federation: external workload -> P03 `Workload`; federated principal -> Core `Principal`; service account -> P03 `ServiceAccount`; STS exchange -> `TokenExchange`.
- AWS workload/AgentCore patterns: IAM role/session credentials map through Core `Principal`/`AccessGrant` and P03 `TemporaryCredential`; agent identity -> `AgentIdentity` with autonomous or delegated access patterns.

## Anti-conflation invariants
`Workload != WorkloadIdentity`; `Workload != ServiceAccount`; `ServiceAccount != ServicePrincipal`; `ServicePrincipal != Application`; `Device != DeviceIdentityRecord`; `Device != Authenticator`; `SPIFFE ID != SVID`; `TrustDomain != IdentityContext`; `TrustDomain != TrustFramework`; `Attestation != Authentication`; `AgentIdentity != AIAgent`; `Sponsor != Delegator` by default.

## Minimum scenarios
1. **SPIFFE workload:** Workload plays `IdentitySubject` and `Principal`; SPIFFE ID is an `Identifier`; SVID is a `Credential`; WorkloadAttestation grounds `IdentityBinding`; authorization acts on the principal.
2. **Device:** Device plays `IdentitySubject`; DeviceIdentityRecord represents the device; a device certificate is a Core Credential; the same device may separately play `Authenticator`.
3. **AI agent:** AIAgent is a SoftwareAgent and may play `IdentitySubject`/`Principal`; AgentIdentity represents it; AgentSponsor carries accountability; delegated access uses Core Delegation while autonomous access uses AccessGrant.

## Wave-7 formalization expectation
P03 imports the Core and may also reuse selected P01 representation concepts through explicit module dependencies. No cross-profile dependency is allowed to redefine the Core identity criterion.