# CM4DI Reading Guide

This guide routes readers through **research surfaces** rather than persona-style navigation.

## Journal contribution and review path

1. `README.md` — current contribution, scope, version map and status.
2. `versions/v1-published/README.md` — published PUB-002 baseline.
3. `versions/v2-journal/README.md` — active PUB-003 extension.
4. `research/JOURNAL_RESEARCH_CONTRACT_2026-08-29.md` — PUB-003 scientific contract and claim ceiling.
5. `publications/PUB002_TO_PUB003_EXTENSION_DELTA.md` — conference-to-journal delta.
6. `evidence/catalogs/README.md` — standards, EU/EUDI, competitors and neighbor-ontology navigation.
7. `conceptualization/source-mining/README.md` — Source Completeness method/status.
8. `STATUS.md` — complete, active and intentionally deferred claims.

## Ontology engineering path

1. `model/journal-v2/CM4DI_CORE_CONCEPT_REGISTRY_v2.csv`
2. `model/journal-v2/CM4DI_CORE_RELATION_REGISTRY_GATE_C.csv`
3. `model/journal-v2/ddd/CONCEPT_DOMAIN_ASSIGNMENT_v2.csv`
4. `model/journal-v2/ddd/CONTEXT_MAP_v2.md`
5. `research/COMPETENCY_QUESTION_REGISTRY_v2.csv`
6. `research/CQ_RELATION_TRACEABILITY_v2.csv`
7. Issue #58 / Draft PR #59 — current formal module candidate.
8. Issue #69 — formal UFO/gUFO-to-OWL projection and OWL-vs-SHACL decisions.

## Standards and framework coverage

Start at `evidence/catalogs/`. The catalogs are reviewer-facing crosswalks; source-level coverage and raw extraction live under `conceptualization/source-mining/`.

## European Digital Identity alignment

Read `evidence/catalogs/EU_REGULATORY_FRAMEWORK_CATALOG.csv`, then Issue #62 and the source-mining rows for the exact legal/ARF version lineage.

## Competing ontology analysis

Read:

- `evidence/catalogs/COMPETING_ONTOLOGY_CATALOG.csv`
- `evidence/catalogs/ACADEMIC_COMPETITOR_CATALOG.csv`
- `evidence/catalogs/NEIGHBOR_ONTOLOGY_CATALOG.csv`
- Issue #64
- Issue #65

Direct competitor and neighboring ontology are intentionally different categories.

## Adjacent research bridges

Read `research/ADJACENT_RESEARCH_BRIDGES.md` for the governed boundary between CM4DI, SemSocialIdentity, Commentium and Newsium.

## Published conference baseline

Use `versions/v1-published/README.md` as the stable landing page. The original root `CM4DI.owl`, `CM4DI-Generation2-Version15.drawio`, field registry and conference case-study files remain at their historical paths. They are comparison/publication-lineage artifacts and are not the current journal-v2 semantic source.

## Canonical distinction

`Domain != Bounded Context != Profile != OWL Module`.
