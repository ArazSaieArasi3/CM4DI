# CM4DI Journal V2 — Machine / Workload / Device / AI-Agent Identity Discovery QC

**Date:** 2026-08-19  
**Scope:** Issue #6 — Machine, workload, device and AI-agent identity discovery

## QC result

**Overall status: PASS — research-grade non-human identity evidence baseline for Gate-B preparation.**

This PASS means the bounded Issue #6 outputs are sufficiently authoritative, current, cross-platform, traceable and semantically differentiated to support the human/non-human scope decision at Gate B. It does **not** mean the emerging AI-agent identity landscape is mature or that every machine-identity technology has been reviewed.

## Quantitative execution summary

- Required discovery areas covered: **5/5** — cloud workload identity/federation; service-account/service-principal patterns; SPIFFE/SPIRE; device identity; AI-agent identity.
- Major operational ecosystems represented: Microsoft Entra, Google Cloud, AWS, Kubernetes, SPIFFE/SPIRE, GitHub Actions.
- Curated evidence records: **20** (`CM4DI-EVID0071`–`CM4DI-EVID0090`).
- Non-human identity semantic candidates: **40** (`CAND-NH-001`–`CAND-NH-040`).
- Explicit anti-conflation rules: **25**.
- Profile architecture decision-support artifact produced: **PASS**.
- Evidence-ID continuity / collision prevention: **PASS** via `evidence/EVIDENCE_STREAM_MANIFEST.md`.
- Canonical `CM4DI.owl` unchanged from `main`: **PASS** — identical Git blob SHA `e04ae62319aac1c123877b0b03acf3f5137a9849`.
- Canonical OntoUML/draw.io baseline unchanged from `main`: **PASS** — identical Git blob SHA `0dce512f4c0611ccaf2fd5665d6148fb379b22af`.

## Quality assessment by dimension

| Dimension | Assessment | Rationale |
|---|---:|---|
| Source authority / provenance | 5.0 / 5 | Evidence uses official Microsoft, Google, AWS, Kubernetes, SPIFFE/SPIRE and GitHub technical documentation/specifications. |
| Recency / status verification | 4.9 / 5 | Current 2026 documentation was used for workload and agent identity; living cloud documentation must be rechecked near submission. |
| Required Issue #6 scope coverage | 5.0 / 5 | Every scope item in Issue #6 is represented with direct primary evidence. |
| Traceability / reproducibility | 4.9 / 5 | Stable IDs, stream registry, concept matrix, candidate register, anti-conflation rules and decision-support artifact are committed. |
| Ontological differentiation | 5.0 / 5 | Workload, workload identity, account, principal, identifier, credential, device record, attestation and AI agent are explicitly separated. |
| Cross-platform normalization | 4.9 / 5 | Vendor terms are normalized without promoting ServiceAccount, ServicePrincipal, ManagedIdentity, SPIFFE ID or Agent Identity mechanically into Core. |
| Human/non-human boundary analysis | 4.9 / 5 | Strong evidence supports broader identity-subject compatibility while avoiding a flat `MachineIdentity` superclass. |
| SPIFFE/device depth | 4.9 / 5 | Identity namespace, SVID, trust bundle, node/workload attestation and device record/credential distinctions are captured. |
| AI-agent evidence maturity | 4.4 / 5 | Microsoft and AWS provide strong current operational evidence, but the field is emergent, product terminology is young, and academic/standard convergence is not yet mature. |
| Contribution to Gate-B readiness | 4.7 / 5 | Non-human scope is now well framed; academic competitors, implementation/datasets and social-identity tracks still need completion before Gate B. |

**Execution-quality estimate:** approximately **4.8/5 (~95–96%)** for the bounded Issue #6 objective. This score assesses execution quality, not ontology completeness.

## Major validated findings

### 1. A flat `MachineIdentity` class would be ontologically weak
The evidence consistently separates the entity doing computation from its account/principal/identity representation, identifier and credential. A workload, service account, service principal, managed identity, SPIFFE ID, SVID and temporary token therefore cannot be placed in a single simple subtype tree.

### 2. CM4DI must support non-human identity subjects without becoming a computing ontology
ISO/enterprise evidence already established devices/software in identity scope; this wave adds workloads, processes, service accounts and agents. The Core should be compatible with non-human identity-bearing entities, while detailed workload/device/agent kinds remain profile-first unless Gate-B/UFO analysis justifies otherwise.

### 3. `Principal` is reinforced as a contextual authorization role
Google, Microsoft, AWS and Kubernetes all authorize principals that may be backed by people, groups, accounts, workloads or federated representations. This strongly supports treating Principal as a contextual security role rather than a person/machine kind.

### 4. Account / identity-representation layer is now cross-wave high confidence
Issue #5 exposed Account/Profile in enterprise IAM. Issue #6 independently confirms ServiceAccount, ServicePrincipal, ManagedIdentity, Device identity record and Agent identity patterns. Gate B should therefore explicitly analyze a neutral representation/account layer distinct from IdentitySubject.

### 5. Attestation and identity binding are missing reusable semantics
SPIRE distinguishes node attestation from workload attestation and binds runtime evidence to identity issuance. Device registration and workload federation provide related evidence-binding patterns. A generic Evidence/Attestation/IdentityBinding abstraction should be evaluated for Core or a shared assurance profile.

### 6. SPIFFE trust semantics must not be conflated with government trust governance
Trust Domain is an identity namespace/security boundary; Trust Bundle contains authoritative cryptographic keys; SPIFFE Federation exchanges trust material. These constructs differ from Trust Framework, Trust Registry/Trusted List and institutional certification discovered in Issue #4.

### 7. Device identity is independent from device-as-authenticator
Microsoft Entra and AWS IoT show devices can have their own registry/directory identity and credentials. The same hardware may also play an authenticator role, but identity-subject and authenticator semantics must remain distinct.

### 8. AI-agent identity is operationally real but should remain profile-first
Microsoft Entra Agent ID distinguishes agent identities from human and application identities and supports autonomous/delegated access and sponsors. AWS AgentCore treats agent identity as specialized workload identity with stable identity across credential/deployment schemes. These sources justify an Agent Profile view, but not yet an AI-specific Core class.

### 9. Delegation is now a strong cross-wave Core candidate
RFC 8693/token exchange previously exposed Actor versus Subject. AI-agent systems now independently require agents acting on behalf of human users. This convergence raises `Delegation` / `actsOnBehalfOf` from a niche profile concern to a high-priority Gate-B Core question.

### 10. Ephemerality is a lifecycle characteristic, not an identity category
Agent/workflow identities can be dynamically created and short lived. This should inform lifecycle/state modeling without making `EphemeralIdentity` a foundational kind solely on duration.

## Residual limitations

1. AI-agent identity is evolving rapidly; Microsoft Entra Agent ID and AWS AgentCore provide strong operational evidence but not a mature cross-industry standard taxonomy.
2. This wave intentionally does not model every IoT/device identity architecture, TPM/TEE attestation system, service mesh or CI/CD provider.
3. SPIFFE/SPIRE is a workload-identity standard/reference implementation, not a foundational ontology; its technical vocabulary remains profile/mapping evidence.
4. Device-management compliance, MDM policy and hardware security detail remain outside CM4DI Core scope.
5. Workload authorization policy languages remain covered by prior authorization evidence; this issue does not replicate full policy analysis.
6. Exact UFO stereotypes for software application, workload/runtime instance, software agent, device and identity/account representations are deferred to Gate B/C conceptual analysis.
7. The non-human evidence subset remains separate until Issue #9 performs cross-stream deduplication and central-registry normalization.

## Exit decision

Issue #6 can be closed as **completed**. The next recommended execution step is **Issue #7 — Reference implementations, GitHub repositories and datasets**, followed by the academic-competitor stream and social-identity side track before Issue #9 Gate-B synthesis. This preserves the rule that canonical OntoUML/OWL is not refactored until cross-stream evidence normalization is complete.