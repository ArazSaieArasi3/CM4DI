# CM4DI Reading Guide

## If you are a journal reviewer
1. `README.md` — current contribution, scope and status.
2. `research/JOURNAL_RESEARCH_CONTRACT_2026-08-29.md` — PUB-003 scientific contract and claim ceiling.
3. `publications/PUB002_TO_PUB003_EXTENSION_DELTA.md` — conference-to-journal delta.
4. `evidence/catalogs/README.md` — standards, EU/EUDI, competitors and neighbor-ontology navigation.
5. `conceptualization/source-mining/README.md` — Source Completeness method/status.
6. `model/journal-v2/ddd/DOMAIN_REGISTRY_v2.csv` and `BOUNDED_CONTEXT_REGISTRY_v2.csv` — DDD ownership.
7. Gate-C concept/relation registries — current conceptual semantics.
8. `STATUS.md` — what is complete, active and intentionally not yet claimed.

## If you are an ontology engineer
1. `model/journal-v2/CM4DI_CORE_CONCEPT_REGISTRY_v2.csv`
2. `model/journal-v2/CM4DI_CORE_RELATION_REGISTRY_GATE_C.csv`
3. `model/journal-v2/ddd/CONCEPT_DOMAIN_ASSIGNMENT_v2.csv`
4. `model/journal-v2/ddd/CONTEXT_MAP_v2.md`
5. `research/COMPETENCY_QUESTION_REGISTRY_v2.csv`
6. `research/CQ_RELATION_TRACEABILITY_v2.csv`
7. Issue #58 / Draft PR #59 for the current formal module candidate.
8. Issue #69 for formal UFO/gUFO-to-OWL projection and OWL-vs-SHACL decisions.

## If you are checking standards/framework coverage
Start at `evidence/catalogs/`. The catalogs are reviewer-facing crosswalks; source-level coverage and raw extraction live under `conceptualization/source-mining/`.

## If you are checking European Digital Identity alignment
Read `evidence/catalogs/EU_REGULATORY_FRAMEWORK_CATALOG.csv`, then Issue #62 and source-mining rows for the exact legal/ARF version lineage.

## If you are comparing CM4DI with other ontologies
Read `evidence/catalogs/COMPETING_ONTOLOGY_CATALOG.csv`, `ACADEMIC_COMPETITOR_CATALOG.csv`, `NEIGHBOR_ONTOLOGY_CATALOG.csv`, then Issue #64/#65. Direct competitor and neighbor ontology are intentionally different categories.

## If you need the historical conference baseline
Use the root `CM4DI.owl`, `CM4DI-Generation2-Version15.drawio`, field registry and conference case-study files. These are historical comparison artifacts and must not be mistaken for the current journal-v2 semantic source.

## Canonical distinction
`Domain != Bounded Context != Profile != OWL Module`.
