# Framework Adoption

CM4DI follows **OGCM-RF — Ontology-Grounded Conceptual Model Repository Framework** for journal-extension research and ontology evolution, and follows **Araz Research Portfolio** for Research/Publication identity, lifecycle, priority, cross-program bridges and execution governance.

**Portfolio identity:** R-015 / P1-L6, bridges P3 and P5, Priority A.  
**Publications:** PUB-002 published conference baseline; PUB-003 active journal extension.  
**OGCM-RF status:** active partial adoption; no full conformance claim yet.  
**Current research stage:** W6.5 retrospective Source Completeness reconciliation before final Wave-7 module/formal-axiom freeze.

## Current machine-readable governance
- Portfolio Manifest 1.1: `.research/manifest.yaml`
- OGCM-RF Implementation Profile 1.0: `.research/ogcm-rf-profile.yaml`
- Semantic CI policy: `.research/semantic-ci-policy.yaml`
- Historical root `REPOSITORY_PROFILE.yaml` is a compatibility pointer only.

## Implemented semantic baseline
- UFO-grounded and OntoUML-specified conceptual model with approved Gate-C semantic freeze.
- Published conference OWL/diagram preserved as historical PUB-002 baseline.
- 134 curated evidence records from the pre-ESM discovery program.
- 34 frozen Core concepts and 55 Core relations.
- 68 governed profile concepts and 65 current profile relations.
- 102 governed concepts and 120 governed Core/profile relations total.
- 52 governed CQs with Domain and relation-resolution traceability.
- 68 governed standards/platform/profile mappings.
- DDD problem space: Digital Identity Management, 15 canonical subdomains, 13 Bounded Contexts.
- Four cross-domain integration Profiles: Enterprise Identity, Verifiable Credential, Technical Identity, Governed Identity.

## DDD governance
CM4DI explicitly distinguishes:
- **Domain/Subdomain** — problem-space knowledge/capability boundary;
- **Bounded Context** — model and Ubiquitous Language ownership boundary;
- **Profile** — cross-domain standards/platform/ecosystem integration view;
- **Ontology Module** — formal packaging/import unit.

`Domain != Bounded Context != Profile != OWL Module` is a governance invariant.

Canonical Domain and Bounded Context names MUST NOT use `and`, `&`, or slash-composed multi-center labels. Historical aliases are retained only for lineage.

## Current OGCM-RF additions adopted after initial journal-v2 design

### Exhaustive Source Mining
OGCM-RF now requires exhaustive mining of material sources before freezing canonical concept inventories, CQs, module boundaries, upper-ontology commitments or formal axioms. CM4DI therefore runs a retrospective Source Completeness reconciliation under Issues #60–#66 and #68.

Canonical package:
- `conceptualization/source-mining/SOURCE_REGISTER.csv`
- `conceptualization/source-mining/SOURCE_COVERAGE.csv`
- `conceptualization/source-mining/RAW_SOURCE_CONCEPTS.csv`
- `conceptualization/source-mining/SOURCE_RECONCILIATION.csv`

Priority source families are EU/EUDI law and architecture, global standards/trust frameworks, direct ontology competitors and neighboring ontologies.

### Source Completeness Gate
Draft PR #59 is structurally valid against the current 102-concept/120-relation registries but is only an **engineering architecture candidate** until Source Completeness and post-ESM semantic regression pass. No formal module/axiom freeze is claimed before that gate.

### Formal ontology quality
Wave 7 must distinguish the authoritative semantic source from generated OWL distributions, document UFO/OntoUML-to-OWL projection decisions, allocate open-world axioms to OWL and integrity/closed-world constraints to SHACL, and bind reasoner/CQ results to exact artifact versions. Issue #69 governs these commitments.

### Semantic CI execution
CM4DI adopts current Portfolio/OGCM-RF risk-proportional semantic CI governance. Validation coverage is not weakened to save Actions minutes; redundant execution is reduced through change-aware risk classes, reusable graph/build artifacts, concurrency cancellation and manual authoritative release/publication gates. Issue #70 and `.research/semantic-ci-policy.yaml` govern this work.

### Manuscript quality
PUB-003 uses Portfolio `ARP::MQAP-EXT` plus the OGCM-RF ontology/conceptual-model quality profile. Journal claims such as `complete`, `comprehensive`, `integrated`, `interoperable`, `reference ontology` and `validated` require explicit evidence and cannot be inferred from class count or scope ambition alone. Issue #67 governs the research contract and conference-to-journal delta.

## External semantic positioning
CM4DI aims to be an **integrated cross-paradigm digital-identity reference ontology**, not an isolated replacement for mature adjacent ontologies. Neighbor-ontology alignment/reuse decisions are governed in #65, initially including UFO/gUFO, ONTrust, PROV-O, W3C ORG, ODRL and DPV.

Reviewer-facing source families are separated into catalog tables under `evidence/catalogs/`: standards, protocols, EU regulatory/EUDI material, global trust frameworks, direct competing ontologies, broader academic competitors and neighboring ontologies.

## Historical and current artifact boundaries
- Root conference-era OWL and diagram remain historical immutable comparison baselines.
- Gate-C concept/relation registries plus DDD alignment are the current conceptual source of truth.
- Draft PR #59 is a pre-OWL module-architecture candidate, not a released ontology.
- No journal-v2 HermiT/ROBOT/SHACL/SPARQL formal PASS has yet been claimed.

## Next framework gate
1. Complete Source Completeness #60 and semantic reconciliation #66.
2. Confirm or amend Draft PR #59 and approve module architecture #58.
3. Execute formal commitments/UFO-to-OWL projection #69.
4. Build modular OWL/SHACL, mappings, executable CQs and semantic CI.
5. Freeze Gate D evaluation design, run Wave 8 evaluation, then bind PUB-003 manuscript claims to exact evaluated/released artifacts.
