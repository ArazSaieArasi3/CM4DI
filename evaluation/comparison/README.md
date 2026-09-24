# CM4DI Comprehensive Comparison and Mapping Program

Owner: Issue #135 (`J2-COMP-01`)

## Purpose
This directory is the publication-grade comparison surface for CM4DI journal-v2. It complements, but does not replace, source-level exhaustive mining. Comparison conclusions may only be frozen after the relevant material sources have sufficient coverage under Issue #60.

## Comparison directions
1. **External → CM4DI**: map source-local constructs to neutral CM4DI concepts, relations, Domains, Bounded Contexts, CQs and formalization implications.
2. **CM4DI → External**: audit every governed CM4DI construct against the external landscape to identify support, specialization, implementation evidence, conflict and genuine gaps.

## Evidence levels
- `normative-primary`
- `regulatory-primary`
- `ontology-primary`
- `peer-reviewed-primary`
- `official-operational`
- `implementation`
- `dataset-evaluation`
- `secondary-support`

Operational products, repositories and datasets are never ontology authority by themselves.

## Mapping predicates
- `exact-correspondence`
- `narrower-than`
- `broader-than`
- `specializes`
- `related-to`
- `implements`
- `implementation-of`
- `bridge-to`
- `partially-overlaps`
- `conflicts-with`
- `anti-equivalent-to`
- `no-correspondence`
- `out-of-scope`

`exact-correspondence` requires explicit semantic evidence. Lexical identity is insufficient.

## Mapping confidence
- `high`: direct definition/axiom/requirement correspondence with no material contradiction.
- `medium`: strong partial correspondence but narrower/broader/contextual differences remain.
- `low`: useful exploratory relation only; not publication-grade without further evidence.
- `blocked`: source material is restricted/inaccessible or coverage is insufficient.

## Mandatory semantic units
Comparison is performed for concepts, relations, roles, events, lifecycle states/transitions, constraints, data/information artifacts, assurance/trust constructs, formal axioms, CQs and implementation realizations.

## DDD governance
`Domain != Bounded Context != Profile != Product != Service != Database != OWL Module`.
Canonical Domain and Bounded Context names contain no `and`, `&`, or slash-composed semantic center.

## Social Identity boundary
Social Identity remains governed by SemSocialIdentity. CM4DI may bridge organization/membership/persona/social constructs where justified, but comparison must not silently merge the scopes. Commentium and other adjacent projects are integration targets, not CM4DI Core owners.

## Publication rule
Do not synthesize heterogeneous dimensions into one arbitrary overall ontology score. Use traceable matrices, coverage counts, gap ledgers and explicit qualitative comparisons.

## Planned outputs
- `COMPREHENSIVE_SOURCE_COMPARISON_MATRIX.csv`
- `CM4DI_TO_EXTERNAL_COVERAGE_MATRIX.csv`
- `EXTERNAL_TO_CM4DI_MAPPING_MATRIX.csv`
- `DOMAIN_BOUNDED_CONTEXT_COVERAGE_MATRIX.csv`
- `CONCEPT_COMPARISON_MATRIX.csv`
- `RELATION_COMPARISON_MATRIX.csv`
- `ROLE_EVENT_LIFECYCLE_MATRIX.csv`
- `CONSTRAINT_ASSURANCE_MATRIX.csv`
- `EQUALITY_COREFERENCE_ALIGNMENT_MATRIX.csv`
- `TRUST_GOVERNANCE_COMPARISON_MATRIX.csv`
- `NONHUMAN_AGENT_IDENTITY_MATRIX.csv`
- `FORMAL_ONTOLOGY_COMPARISON_MATRIX.csv`
- `REUSE_IMPORT_BRIDGE_DECISION_MATRIX.csv`
- `REASONING_CQ_EVALUATION_MATRIX.csv`
- `IMPLEMENTATION_DATASET_COVERAGE_MATRIX.csv`

## Execution status — 2026-09-24
- #136 direct competitors: ACTIVE; governed competitor catalog loaded into comparison workspace.
- #137 neighbor ontologies: ACTIVE; provisional reuse/import/bridge decisions loaded.
- #138 standards/EUDI/trust frameworks: ACTIVE; current normative family baseline and EUDI crosswalk loaded.
- #139 operational ecosystems: QUEUED behind active deep-dives, with profile/cloud mappings already represented.
- #140 reverse coverage: ACTIVE; all 102 governed concepts, 120 governed relations and 13 Bounded Contexts now have explicit reverse-audit rows.
- #141 manuscript synthesis: PROVISIONAL baseline exists; final table selection remains blocked on #60/#66.

Full publication conclusions remain deferred until active deep-dives provide sufficient source coverage. The workspace is now populated enough to expose gaps rather than merely define schemas.