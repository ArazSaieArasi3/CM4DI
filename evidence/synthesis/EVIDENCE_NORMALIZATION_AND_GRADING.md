# CM4DI Journal V2 — Evidence Normalization and Grading

## Scope
This artifact consolidates the completed discovery streams for Gate B without duplicating their full registries. Stream-specific registries remain authoritative for detailed provenance. The synthesis layer records cross-stream deduplication, version/status normalization, evidence weighting, and retained coverage.

## Retained evidence inventory

| Stream | Evidence IDs | Count | Gate-B role | Normalization status |
|---|---:|---:|---|---|
| Normative standards/protocols | `CM4DI-EVID0001`–`0029` | 29 | normative semantics / protocol distinctions | Retained; supersession/status already audited |
| Government/trust frameworks | `CM4DI-EVID0030`–`0045` | 16 | legal/governance/trust ecosystem semantics | Retained; jurisdiction-specific labels normalized to neutral patterns |
| Enterprise/cloud IAM/SSO | `CM4DI-EVID0046`–`0070` | 25 | operational semantics / terminology convergence | Retained; vendor terms normalized to neutral candidates |
| Machine/workload/device/agent | `CM4DI-EVID0071`–`0090` | 20 | non-human subject and runtime identity semantics | Retained; platform-specific labels separated from ontology categories |
| Implementations/conformance/datasets | `CM4DI-EVID0091`–`0105` | 15 | executable conformance, realism, instantiation feasibility | Retained; evidence role kept distinct from conceptual authority |
| Academic/competitor literature | `CM4DI-EVID0106`–`0120` | 15 | scholarly convergence, novelty and competitor positioning | Retained; bounded scholarly corpus, not exhaustive SLR |
| Social-identity boundary | `CM4DI-EVID0121`–`0134` | 14 | scope exclusion / bridge and future-work decisions | Retained as segregated side-track evidence |
| **Total** |  | **134** |  | **Gate-B complete** |

## Cross-stream deduplication result
No retained item was removed solely because it came from the same ecosystem as another item. Deduplication was performed at the level of the evidence artifact and semantic role, not organization name. For example, a W3C Recommendation, a W3C conformance test suite and a scholarly paper discussing the same technology are distinct evidence types and remain separately traceable.

Potential duplicates were handled by these rules:
1. exact same source/version -> retain one evidence ID and reference it from multiple candidate families;
2. superseded normative version -> retain historical record only when needed for traceability; current semantics use the active/successor source;
3. mirror vs upstream repository -> treat upstream as authority and mirror as access/verification only;
4. vendor documentation pages describing the same object family -> normalize to one semantic candidate rather than counting each page as an independent concept;
5. review papers vs primary sources -> reviews support convergence/coverage, while normative or primary operational sources govern exact semantics;
6. datasets duplicated on Kaggle or secondary mirrors -> use original DOI/institutional source only.

## Multidimensional evidence grading
Evidence is not collapsed into a single synthetic score. Gate-B reasoning uses six dimensions:

- **Authority** — normative body, government/institution, peer-reviewed scholarship, official implementation, secondary source.
- **Recency/status** — current, transitional, superseded, living documentation requiring recheck.
- **Semantic directness** — whether the source directly defines the construct or only discusses it.
- **Cross-ecosystem recurrence** — whether the same distinction recurs independently across streams.
- **Operational executability** — availability of implementation, test suite, data or runnable scenario.
- **Ontology utility** — whether the source helps distinguish kinds, roles, relators, events, information objects, qualities or mappings.

### Evidence tiers used for candidate decisions
- **Tier A — Admission-strength:** current normative/institutional primary source plus independent cross-stream recurrence, or equivalent peer-reviewed foundational evidence with operational corroboration.
- **Tier B — Profile-strength:** strong evidence but ecosystem/paradigm-specific, operationally useful, or not sufficiently universal for Core.
- **Tier C — Mapping/context strength:** useful for mappings, evaluation, terminology or future work but insufficient to define a CM4DI Core primitive.

## Gate-B admission rule
A normalized candidate is recommended for **Core** only when all are true:
1. the semantics are protocol/vendor neutral;
2. the distinction is necessary for more than one identity paradigm or for a foundational anti-conflation rule;
3. the concept/relation supports a competency question or interoperability mapping that the existing baseline cannot answer cleanly;
4. it can be grounded coherently under UFO/OntoUML without importing a complete neighboring ontology;
5. promotion does not make CM4DI human-only, SSI-only, government-only or IAM-vendor-specific.

Candidates that fail universality but remain important are placed in one of four governed profiles. Research metadata, full privacy/social-identity semantics, vendor taxonomies and ambiguous lexical groupings are deferred/rejected rather than forced into Core.

## Version/status normalization notes
- NIST SP 800-63 Rev. 4 is the active NIST baseline for this journal program; older revisions are contextual only.
- ISO/IEC 24760 2025 editions supersede earlier conceptual/reference-architecture editions for current terminology.
- OpenID4VP 1.0, OpenID4VCI 1.0 and OpenID Federation 1.1 are treated as current published anchors in their respective families.
- EUDI ARF remains a living architecture source and must be rechecked near submission.
- UK DVS Trust Framework remains transition-sensitive and must be rechecked against its effective status near submission.
- Product/cloud documentation and AI-agent identity material are living sources and require a final status verification before Gate E.

## Epistemic separation retained for evaluation
- Standards/frameworks define normative semantics.
- Scholarly literature provides theoretical convergence, alternatives and novelty boundaries.
- Operational IAM platforms test whether abstractions survive real implementation vocabularies.
- Reference implementations/conformance suites test executable mappings.
- Datasets test instantiation, trace queries and representational capacity.
- None of these evidence types alone proves ontology correctness.
