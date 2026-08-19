# CM4DI Journal V2 — Machine / Workload / Device / Agent Profile Decision Support

**Status:** pre-Gate-B synthesis for Issue #6. No canonical ontology changes.

## 1. Recommended architecture
Keep the journal architecture as **stable Core + Machine/Workload/Device/Agent Profile**, but structure this profile internally into four coordinated views:

### A. Workload Identity View
Candidate concepts/patterns:
- Workload / Runtime Instance
- Workload Identity
- Service Account
- Principal
- Federated Workload Principal
- Temporary Credential
- Token Exchange
- Workload Identity Federation
- Workload Identity Pool / Namespace
- Workload Identity Provider

### B. SPIFFE / Runtime Attestation View
Candidate concepts/patterns:
- SPIFFE ID
- SVID
- Trust Domain
- Trust Bundle
- Issuing Authority
- Node Attestation
- Workload Attestation
- Attestation Evidence
- Workload API / identity-delivery mapping

### C. Device Identity View
Candidate concepts/patterns:
- Device
- Device Identity Record
- Device Registration / Join
- Device Credential
- Device State / Trust State
- relation: device `representedBy` identity record
- relation: device `uses` credential
- relation: device `playsRole` Authenticator where applicable

### D. AI Agent Identity View
Candidate concepts/patterns:
- Software Agent / AI Agent
- Agent Identity
- Agent Sponsor / Owner
- Autonomous Access
- Delegated Agent Access
- Agent lifecycle / ephemerality
- Agent Blueprint / identity template as mapping/profile artifact
- Tool / external-resource access mapping

## 2. Strongest Core implications
The evidence does not justify moving vendor-specific machine terms into Core. It **does** justify testing whether the Core needs these neutral abstractions:

1. **Broader identity-bearing substrate / IdentitySubject semantics** so devices, software/workloads and agents can participate without pretending they are persons or organizations.
2. **Principal** as an authorization-context role distinct from the underlying entity/account.
3. **Generic Account / Identity Representation** semantics, already strongly supported by Issue #5, so service accounts, agent identities and device records can specialize/match without becoming identity subjects themselves.
4. **Generic Evidence / Attestation / Identity Binding** semantics connecting entity/runtime evidence to identity issuance or registration.
5. **Generic Delegation / actsOnBehalfOf** semantics because both token exchange and AI agents require an actor distinct from the represented/delegating subject.
6. **Credential lifecycle** capable of representing short-lived/rotating machine credentials while identity remains stable.
7. **Generic Federation** broad enough for workload federation as well as human federation, with profile-specific mechanisms.

## 3. Concepts that should remain profile-first
Even when highly important operationally, the following should not be Core by default:
- Workload
- Service Account
- Service Principal
- Managed Identity
- Workload Identity Pool
- SPIFFE ID / SVID
- Trust Bundle
- Device Identity Record
- Agent Identity
- Agent Sponsor
- Agent Blueprint
- autonomous-agent access mode

Their semantics can be expressed by shared Core primitives plus profile specializations/mappings.

## 4. Candidate relations requiring UFO analysis
- `represents(DigitalIdentity/Account, IdentityBearingEntity)`
- `identifies(Identifier, IdentityBearingEntity or IdentityRepresentation)`
- `boundTo(IdentityRepresentation, Workload/Device/Agent)`
- `attestsTo(Evidence/Attestation, Entity/RuntimeProperty)`
- `grounds(Attestation, IdentityBinding/Issuance)`
- `usesCredential(Principal/IdentityRepresentation, Credential)`
- `federatesAs(ExternalIdentity, FederatedPrincipal)`
- `actsOnBehalfOf(Actor, DelegatingSubject)`
- `sponsoredBy(AgentIdentity/Agent, Sponsor)`
- `playsPrincipalRole(Entity/Account, AuthorizationContext)`

These relation names are provisional and must be normalized during conceptual modeling.

## 5. Key Gate-B decisions

### Decision NH-A — IdentitySubject breadth
**Recommended direction:** preserve one generic participation concept for being the subject of identity information, but do not assume a common rigid superclass such as Party if UFO analysis shows persons/organizations/devices/software differ fundamentally. Treat `IdentitySubject` as a likely role unless contrary evidence emerges.

### Decision NH-B — Account / representation layer
**Recommended direction:** introduce or refine a neutral representation/account layer distinct from IdentitySubject. This is now supported by enterprise IAM, device identity and agent identity evidence.

### Decision NH-C — Principal
**Recommended direction:** treat Principal as a contextual security/authorization role, not a kind of person or machine. It may be played by user/account/group/workload representations depending on system.

### Decision NH-D — Workload as Core vs Profile
**Recommended direction:** profile-first. Core must support non-human subjects, but naming `Workload` in Core risks importing computing/deployment ontology into a cross-domain identity ontology.

### Decision NH-E — Device as Core vs Profile
**Recommended direction:** Core-compatible but likely profile/domain kind. Device identity is clearly real, yet CM4DI can remain reusable if external/device kinds play IdentitySubject and profile semantics provide device registration/state.

### Decision NH-F — Agent as Core vs Profile
**Recommended direction:** profile-first. Agent-specific identity is now operationally real, but the evidence base is still emerging and product-driven. Generic delegation/actor/principal semantics belong deeper than `AI Agent` itself.

### Decision NH-G — Attestation
**Recommended direction:** generic evidence/binding abstraction should be evaluated for Core; node/workload/device attestation mechanisms stay profile-specific.

### Decision NH-H — Trust Domain
**Recommended direction:** shared Trust profile candidate, not immediate Core. Explicitly distinguish security identity namespace from government Trust Framework and IdentityContext.

## 6. Journal-contribution implication
This wave strengthens the journal novelty argument: CM4DI can position itself as a **cross-paradigm identity ontology that spans human, organizational and non-human identities without collapsing infrastructure accounts, principals, identifiers and credentials into the identity-bearing entities themselves**. The contribution is not a catalog of cloud products; it is the semantic normalization layer across them.

## 7. Deferred questions
- Exact UFO stereotypes for software application, runtime workload, software agent and device.
- Whether `Account` is an information object, social object, functional complex, relator-backed representation, or another pattern in the chosen foundational treatment.
- Whether IdentitySubject should be retained as current class, remodeled as role, or split with a broader bearer abstraction.
- Whether delegation requires an explicit relator/event pattern or a contextual relation tied to Authorization.
- Whether generic `Attestation` belongs in Core or a shared assurance profile.

These are Gate B/C tasks, not discovery tasks.