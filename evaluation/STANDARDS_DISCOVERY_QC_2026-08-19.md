# CM4DI Journal V2 — Standards Discovery Quality-Control Report

**Date:** 2026-08-19  
**Scope:** Issue #3 — Normative standards and protocols discovery

## QC result

**Overall status: PASS — research-grade discovery baseline for Gate-B preparation.**

This PASS means the Issue #3 outputs are sufficiently authoritative, current, traceable and semantically analyzed to feed later synthesis. It does **not** mean that Gate B is complete or that every possible identity specification in existence has been exhaustively enumerated.

## Quantitative execution summary

- Standards-development / authoritative families explicitly required by Issue #3 covered: **7/7** — ISO/IEC, NIST, W3C, IETF, OASIS, OpenID Foundation, FIDO Alliance.
- Curated high-value normative evidence records added to the central Evidence Registry: **29** (`CM4DI-EVID0001`–`CM4DI-EVID0029`).
- Standards-driven concept/relation candidates registered: **36**.
- Separate high-priority semantic collision families documented: **14**.
- Stable/current versus draft/monitor status explicitly distinguished: **PASS**.
- Supersession/revision relationships explicitly recorded for major families: **PASS**.
- Canonical `CM4DI.owl` unchanged from `main`: **PASS** — identical Git blob SHA `e04ae62319aac1c123877b0b03acf3f5137a9849`.
- Canonical OntoUML/draw.io baseline unchanged from `main`: **PASS** — identical Git blob SHA `0dce512f4c0611ccaf2fd5665d6148fb379b22af`.
- Canonical ontology modified before Gate B: **NO**.

## Quality assessment by dimension

| Dimension | Assessment | Rationale |
|---|---:|---|
| Source authority / provenance | 5.0 / 5 | Retained claims were verified against official SDO/institutional sources; no secondary summary is used as ontology-admission evidence. |
| Recency / status verification | 5.0 / 5 | 2025–2026 changes were checked, including ISO 24760:2025, ISO 23220:2026 parts, NIST Rev.4, VC 2.0, OpenID4VC finals, OpenID Federation 1.1, AuthZEN 1.0, SCIM RFC 9967, CTAP 2.3 and active W3C drafts. |
| Required Issue #3 scope coverage | 5.0 / 5 | All seven required standards/protocol families are represented with identity-relevant standards. |
| Traceability / reproducibility | 4.8 / 5 | Stable evidence IDs, URLs/DOIs where available, candidate register, status map and separate ambiguity register are committed on `journal-v2`. |
| Ontology relevance / semantic extraction | 4.7 / 5 | Extraction goes beyond vocabulary listing and identifies missing concepts, role conflicts, lifecycle distinctions and authorization/federation gaps. |
| Semantic caution / anti-conflation | 5.0 / 5 | Verifier, Credential, Assertion, Claim, Subject, Holder, Subscriber, Controller, Evidence/Proof and Context collisions are explicitly prevented from premature merging. |
| Depth of normative clause analysis | 4.1 / 5 | Open specifications were inspected directly; ISO full normative text is not fully open, so ISO extraction is constrained to official public scope/abstract/metadata unless licensed full text is later supplied. |
| Readiness for Gate B | 4.3 / 5 | Standards evidence is ready, but Gate B must still integrate academic, government/trust-framework, operational IAM, machine identity, datasets and social-identity tracks. |

**Execution-quality estimate:** approximately **4.7/5 (94%)** for the bounded Issue #3 objective. This is an assessment of process/output quality, not a claim that the future ontology is already 94% complete.

## Major validated findings

### 1. Proofing is under-modeled in the conference baseline
NIST Revision 4 explicitly distinguishes Applicant, Identity Evidence, Identity Proofing and Enrollment. CM4DI currently models Enrollment but lacks first-class Identity Evidence and Identity Proofing. This is a high-confidence Gate-B candidate gap.

### 2. Authorization is under-specified for cross-standard interoperability
ISO/IEC 29146, XACML 3.0 and OpenID AuthZEN converge on a structure containing Subject/Principal, Resource, Action, Context and Decision. CM4DI currently centers Authorization on claim evaluation and a result. Resource, Action and request/decision context are therefore high-confidence candidates.

### 3. Federation needs a semantic structure, not only provider roles
NIST federation, SAML, OIDC and OpenID Federation jointly support explicit Federation and Assertion concepts. OpenID Federation further introduces Federation Entity, Entity Statement/Configuration, Trust Chain, Trust Anchor and Federation Policy. These should be split between Core and profiles rather than compressed into `TrustReference`.

### 4. Credential lifecycle needs a generic layer
W3C credential status, ISO mobile eID, OpenID4VC issuance and SCIM lifecycle events repeatedly expose issuance, status, suspension/revocation, activation/deactivation or related state changes. Generic lifecycle semantics should be considered while concrete protocol mechanisms remain in profiles.

### 5. Non-human scope is supported by current normative evidence
ISO/IEC 24760-2:2025 explicitly spans individuals, organizations, devices and software. This supports keeping the identity-bearing substrate broad enough for later workload/device/agent discovery rather than hard-coding human-only assumptions.

### 6. Existing class names need semantic review
The strongest collision is `Verifier`: NIST authentication verifier and VC verifier are not automatically the same role. Similar issues exist for Credential, Assertion, Claim, Subject, Holder/Subscriber and IdP/RP rigidity. These are now registered for Gate B rather than silently normalized.

## Residual limitations

1. ISO extraction is based on official public descriptions and metadata where full clauses are paywalled; full-clause validation can be added if licensed copies are supplied.
2. Issue #3 is a bounded normative review, not a systematic review of all academic literature; Issue #2 covers competing scholarly models.
3. EUDI/eIDAS and national trust frameworks are intentionally deferred to Issue #4.
4. AWS/Entra/Google/Okta/Keycloak operational terminology and implementation evidence are intentionally deferred to Issue #5.
5. Workload/device/agent identity is intentionally deferred to Issue #6.
6. The 29-item central evidence subset prioritizes ontology-relevant sources; lower-level security/format extensions remain discoverable in the broader inventory instead of bloating the curated registry.

## Exit decision

Issue #3 can be closed as **completed**. The next recommended execution step is Issue #4 — Government digital identity and trust-framework discovery — because the standards wave has surfaced unresolved Trust Anchor, Trust Chain, assurance, governance and wallet-framework questions that government/EUDI evidence is best positioned to resolve.