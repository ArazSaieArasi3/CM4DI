# CM4DI Journal V2 — Research and Ontology Roadmap

## Objective
Evolve CM4DI from the published PUB-002 conference baseline into a publication-ready, reproducible, cross-paradigm digital-identity reference ontology, governed by current Araz Research Portfolio and OGCM-RF practices.

## Architectural invariants
- Gate-C Core semantics remain stable unless new material evidence demonstrates a genuine defect.
- Domain != Bounded Context != Profile != OWL Module.
- Canonical Domain/Bounded Context names do not use `and`, `&`, or slash-composed semantic centers.
- Social Identity remains outside CM4DI except explicit bridge mappings; Social Login is federation/authentication.
- No `MachineIdentity` superclass.
- Standards, products and datasets are evidence/mapping/evaluation inputs, not automatic ontology authorities.
- Mature neighbor ontologies should be reused/aligned/bridged instead of duplicated without justification.

## Wave 0 — Governance and baseline — COMPLETE
Conference baseline preservation; `journal-v2`; OGCM-RF scaffold; stable IDs; evidence protocol; research mission/RQs; version/release policy.

## Waves 1–4 — Evidence discovery — COMPLETE AS ORIGINAL DISCOVERY PROGRAM
Academic/ontology literature; ISO/NIST/W3C/IETF/OASIS/OpenID/FIDO; EUDI and government trust frameworks; enterprise/cloud IAM; workload/device/agent identity; reference implementations; datasets; segregated Social Identity.

Original result: 134 curated evidence records. This remains valid evidence but predates mandatory OGCM-RF Exhaustive Source Mining.

## Gate B — Evidence and Scope Lock — APPROVED
201 raw candidate families → 75 normalized decision families; Core/Profile/Deferred/Reject/Social-Future dispositions; novelty and scope baseline.

## Wave 5 — Conceptual Model Revision — COMPLETE
34 frozen Core concepts/patterns, 55 Core relations, 32 Core CQs, UFO/OntoUML review, anti-pattern review.

## Gate C — Conceptual Model Freeze — APPROVED
Retained after DDD alignment amendment and regression review.

## Wave 6 — Profiles and Mappings — COMPLETE
- P01 Enterprise Identity Profile
- P02 Verifiable Credential Profile
- P03 Technical Identity Profile
- P04 Governed Identity Profile

Current governed totals after regression repair: 68 profile concepts, 65 profile relations, 68 mappings, 20 profile CQs; 52 CQs total.

## DDD Alignment Amendment — COMPLETE
Issues #50–#57.
- Overall Domain: Digital Identity Management.
- 15 canonical subdomains.
- 13 Bounded Contexts.
- Four Profiles are cross-domain integration views.
- All 102 concepts, 120 relations, 52 CQs and 68 mappings are traceable through current DDD ownership.

## Wave 6.5 — Retrospective Source Completeness Reconciliation — ACTIVE
**Parent:** #60. This wave was added because OGCM-RF made Exhaustive Source Mining and a Source Completeness Gate mandatory on 2026-08-28.

### W6.5 workstreams
- #61 Material-source inventory and coverage registry.
- #62 EU/EUDI regulatory and architecture exhaustive mining.
- #63 Global standards, protocols and trust-framework exhaustive mining.
- #64 Direct competing ontology and closest-work revalidation.
- #65 Neighbor ontology reuse/alignment catalog.
- #66 Source reconciliation and post-ESM semantic regression.
- #68 Reviewer-facing standards/framework/ontology/literature catalogs.
- #67 MQAP-EXT PUB-002→PUB-003 research-contract and contribution lock runs in parallel and consumes #64/#65 results.

### Source Completeness Gate
Before formal module/axiom freeze, every material source must be complete, explicitly blocked/qualified, or documented as non-concept-bearing; raw extractions must have semantic dispositions; unresolved material conflicts must be zero or explicitly decision-gated.

## Wave 7 — Formal Ontology and Automation — STARTED BUT FORMAL FREEZE BLOCKED ON W6.5

### W7-01 module architecture candidate
Issue #58 / Draft PR #59 already provide a structurally validated candidate:
- 12 formal modules + 4 non-owning aggregate Profile entrypoints;
- 102/102 concept ownership;
- 120/120 relation ownership;
- 0 duplicate/unowned IDs;
- 0 import cycles;
- 0 Core→extension imports.

**Status:** engineering baseline candidate, not frozen. Source Completeness #60/#66 must pass before PR #59 approval/merge.

### Formal work after source-complete module approval
- #69 Formal ontology commitments and UFO/gUFO-to-OWL projection.
- I01 authoritative formal source, ontology/version IRIs and module manifests.
- I02 OWL 2 DL axiomatization.
- I03 SHACL constraints and OWL-vs-SHACL allocation.
- I04 deterministic serializations.
- I05 machine-readable neighbor/standards mappings.
- I06 ROBOT/HermiT or equivalent logical checks.
- I07 SPARQL implementation of 52 governed CQs.
- I08 machine-readable examples/scenarios.
- I09 documentation and Mermaid review views.
- #70 cost-aware semantic CI and SHA-bound validation evidence.

## Gate D — Evaluation Design Lock
Freeze evaluated semantic release/module graph, representative standards/frameworks, direct competitors, neighbor ontologies, platforms, datasets, CQs, scenarios, metrics, reasoner/SHACL tooling and expert protocol if used.

## Wave 8 — Multi-layer Evaluation
- Syntax/serialization and OWL profile.
- Logical consistency and satisfiability.
- UFO/OntoUML grounding and anti-pattern evaluation.
- SHACL structural/integrity evaluation.
- CQ/SPARQL evaluation.
- Standards/protocol coverage.
- EU/EUDI legal/architecture coverage.
- Enterprise IAM mapping experiment.
- Verifiable Credential ecosystem mapping.
- Workload/device/agent mapping.
- Trust/government mapping.
- Neighbor-ontology interoperability/alignment assessment.
- Cross-paradigm scenarios.
- Dataset-based instantiation/mapping.
- Strongest-competitor comparative benchmark.
- Expert assessment if methodologically useful.
- Reproducibility and threats-to-validity analysis.

## Wave 9 — PUB-003 Journal Manuscript and Scholarly Release
Governed by #67 and ARP::MQAP-EXT.
- PUB-002→PUB-003 scientific delta matrix.
- Closest-work/novelty statement after #64.
- Source-complete related-work and standards/framework tables.
- Methodology: DSR + ESM + UFO/OntoUML + DDD + modular formal ontology engineering + layered evaluation.
- Core/Domain/Context/Profile/module specification.
- EU/EUDI and global standards/framework crosswalks.
- Neighbor-ontology integration architecture.
- Formal ontology results.
- Evaluation results and comparative benchmark.
- Discussion, limitations, claim calibration and reproducibility.
- Exact manuscript↔evaluated release↔repository binding.
- Versioned release, persistent scholarly archive/DOI where feasible.

## Gate E — Submission Lock
Final approval of target journal, manuscript, contribution/overlap audit, exact ontology release, evaluation package, references, figures, supplementary materials and declarations.

## Current next action
Execute Wave 6.5 in priority order: #61 → #62/#63/#64/#65 → #68 → #66. In parallel maintain #67 journal positioning. Only after Source Completeness PASS confirm/amend and approve #58/#59, then execute #69 and the remaining Wave-7 formalization stack.
