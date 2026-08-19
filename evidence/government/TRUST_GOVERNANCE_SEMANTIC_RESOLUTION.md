# CM4DI Journal V2 — Trust and Governance Semantic Resolution

**Status:** Gate-B decision support; no ontology admission yet.

## Problem
The conference baseline contains `TrustReference` and alignment to `ONTrust:Trust`. Government/trust-framework discovery shows that mature ecosystems use several different constructs that must not be collapsed into one generic notion of trust.

## Required distinctions

### 1. Trust relation / trust assessment
The ontological phenomenon of one party relying on or assessing another party/object in a context. This is the layer most closely related to the existing ONTrust alignment. It is not equivalent to certification or registry membership.

### 2. Trust Framework
A governed set of rules, requirements, roles, conformance expectations and procedures defining what trustworthy participation means in an ecosystem. Examples include the UK DVS Trust Framework and Canada's PCTF.

**Key relation candidates:**
- `governs(Ecosystem/Participation)`
- `definesRole(ProviderRole)`
- `definesConformanceRequirement(Requirement)`
- `recognizedBy(GovernanceAuthority)`

### 3. Trust Registry / Trusted List
A governed information service or artifact exposing status information about participants, providers, trust services, credentials or certificates. It can be queried to determine whether an entity/service has a current governed status.

**Key relation candidates:**
- `records(Participant/Service)`
- `recordsStatus(ParticipantStatus)`
- `maintainedBy(Registrar/GovernanceAuthority)`
- `evidences(Certification/RegistrationStatus)`

A registry/list is **not** itself the trust framework and is **not** a cryptographic root.

### 4. Trust Anchor
An authoritative validation root (often represented through cryptographic material plus associated data) from which a validation path/chain can be established. EUDI ARF and OpenID Federation evidence support this construct.

**Key relation candidates:**
- `anchors(TrustChain/ValidationPath)`
- `recognizedBy(TrustDomain/Framework)`

A trust anchor is **not** a registry, certification status or social trust relation.

### 5. Conformance / Accreditation / Certification
Processes and resulting statuses that establish that a provider/service conforms to specified requirements. These are governance events/relators and states, not trust itself.

**Key relation candidates:**
- `assessesAgainst(Framework/Profile)`
- `performedBy(ConformityAssessmentBody/Regulator)`
- `resultsIn(CertificationStatus/AccreditationStatus)`
- `appliesTo(Service/Provider)`

### 6. Ecosystem Participation / Registration
The governed relationship by which an actor/service becomes eligible to participate in an identity ecosystem. Registration, recognition, approval and certification may be prerequisites but are not necessarily equivalent.

## Implication for existing `TrustReference`
`TrustReference` should not become a catch-all superclass for the constructs above. The most defensible Gate-B direction is to preserve it as a lightweight reference/information object that can point to or identify relevant trust/governance resources, while introducing explicit profile constructs where semantic reasoning requires them.

Potential future mappings:
- `TrustReference -> references -> TrustFramework`
- `TrustReference -> references -> TrustRegistry/TrustedList`
- `TrustReference -> references -> TrustAnchor`
- `TrustReference -> references -> Certification/AssuranceScheme`

This preserves the conference model's lightweight alignment while enabling the journal extension to represent governance structures explicitly.

## Relationship to `ONTrust:Trust`
The ONTrust-aligned trust concept should remain semantically distinct from institutional conformance and cryptographic validation infrastructure. At Gate B/C, the model should verify whether `ONTrust:Trust` captures a social/relational trust phenomenon and then connect governance evidence to that layer through justified relations (for example, certification or registry status may provide evidence that informs trust, but should not be asserted as identical to trust).

## Gate-B questions
1. Is `TrustFramework` needed in Core as a neutral context/reference target, or only in the Trust/Government Profile?
2. Should `TrustRegistry` and `TrustedList` share a generic `TrustStatusRegistry` abstraction?
3. Is `TrustAnchor` sufficiently cross-paradigm for a common Trust Profile, or should it remain federation/wallet specific?
4. Should accreditation and certification share a generic `ConformityAssessment` pattern?
5. What minimum governance constructs are required to answer competency questions without turning CM4DI into a full governance/compliance ontology?

## Recommended boundary
CM4DI should model enough governance to explain **why a provider, credential, assertion or wallet can be relied upon across ecosystems**, while external legal, compliance, audit, privacy and certification rule detail remains outside the Core and is linked through profiles/mappings.