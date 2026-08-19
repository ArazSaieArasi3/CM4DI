# CM4DI Journal V2 — Non-Human Identity Anti-Conflation Rules

**Status:** Gate-B decision support; no ontology admission yet.

## Purpose
Non-human identity terminology is unusually overloaded across cloud IAM, Kubernetes, SPIFFE/SPIRE, device management and emerging AI-agent platforms. This document records semantic collisions that must be resolved ontologically rather than lexically.

## High-priority rules

1. **Workload ≠ Workload Identity.** A workload performs computation; workload identity is a representation enabling authentication/authorization.
2. **Application ≠ Application Instance ≠ Service Principal.** A durable application definition can have tenant/deployment-specific identity/security-principal representations.
3. **Service Account ≠ Service Principal.** Kubernetes service accounts and Entra service principals have different identity criteria and lifecycle semantics.
4. **Managed Identity ≠ Workload.** Managed identity is a credential-managed identity representation for a workload/resource, not the software execution itself.
5. **Principal ≠ IdentitySubject.** Principal is contextual to security/authorization and may be played by accounts, users, groups or workload representations.
6. **Device ≠ Device Identity Record.** A physical/virtual device is distinct from its directory/registry representation.
7. **Device ≠ Authenticator.** A device may play an authenticator role but can also be independently identified/managed as a device.
8. **Device Credential ≠ Device Identity.** Certificate/token used to authenticate a device is evidence/credential, not the device or directory identity.
9. **SPIFFE ID ≠ SVID ≠ Workload.** SPIFFE ID is an identifier; SVID is a verifiable identity document; workload is the identified compute entity.
10. **Trust Domain ≠ Trust Framework ≠ IdentityContext.** SPIFFE trust domain is an identity namespace/security trust root; government Trust Framework is governance rules; IdentityContext scopes digital identity semantics.
11. **Trust Bundle ≠ Trust Registry/Trusted List.** Bundle is cryptographic public-key material; registry/list exposes governed status.
12. **Node Attestation ≠ Workload Attestation.** Host/node and process/workload are different targets with distinct evidence.
13. **Attestation ≠ Authentication.** Attestation establishes evidence about entity/runtime properties and may support identity issuance/binding; authentication proves/validates identity in an interaction.
14. **Provisioning ≠ Workload Attestation ≠ Enrollment.** Provisioning creates/synchronizes representations; attestation evaluates runtime evidence; enrollment establishes subscriber/identity-provider participation.
15. **Temporary Credential ≠ Session ≠ Durable Access Grant.** Short-lived token/certificate, interaction/security session and durable permission assignment have different lifecycle/identity criteria.
16. **Token Exchange ≠ Identity Transformation.** Exchanging a credential/token usually changes representation/security context, not necessarily the underlying identity subject.
17. **Workload Federation ≠ Human SSO Federation.** They may share generic federation primitives but subjects, authenticators, lifecycle and trust mechanics differ.
18. **Administrative Identity Pool/Namespace ≠ IdentityContext.** Pool/namespace manages identities; IdentityContext expresses semantic scope of a digital identity.
19. **AI Agent ≠ Human User.** Even when an agent is paired with a user-like account for compatibility, the agent remains a non-human software entity.
20. **AI Agent ≠ Agent Identity.** Agent is software; agent identity is its digital identity/account representation.
21. **Agent Sponsor ≠ Agent Subject.** Sponsor/owner is an accountable human/organization role, not the agent itself.
22. **Autonomous Access ≠ Delegated Access.** Direct permissions of an agent differ from acting on behalf of a human subject.
23. **Actor ≠ Subject under delegation.** The agent/workload performing an action can differ from the human/entity whose authority is delegated.
24. **Ephemeral ≠ Different ontological kind.** Short lifetime is a temporal/lifecycle characteristic and must not be used as the sole basis for introducing a new kind.
25. **Credential-managed identity ≠ credential-free identity.** Managed identities reduce explicit secret management but still rely on issued tokens/credentials during access flows.

## Cross-wave links
These rules reinforce earlier findings:
- Issue #3: `Actor` versus `Subject`, `Delegation`, `TrustAnchor`, `Federation`, `Temporary/Protocol Artifacts`.
- Issue #4: Trust Framework/Registry/Anchor separation and governance status.
- Issue #5: Account/Profile, Principal, Session, Assignment/Grant, IdentitySource versus IdP, and IAM Role versus UFO Role.

## Gate-B consequence
No machine/device/agent term should be added to CM4DI Core because a vendor or standard labels it as an identity. Gate B must decide whether the term denotes:
- an identity-bearing entity;
- a contextual role;
- a digital identity/account representation;
- an identifier;
- a credential/evidence artifact;
- a lifecycle event/state;
- a trust/security context;
- or a profile-specific implementation construct.
