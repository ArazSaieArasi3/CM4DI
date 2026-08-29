# CM4DI Exhaustive Source Mining

## Status
Active retrospective reconciliation under Issue #60. This package upgrades the pre-existing 134-item evidence program to the OGCM-RF Exhaustive Source Mining and Source Completeness Gate introduced on 2026-08-28.

## Governing rule
A source may support CM4DI without being material enough for section-by-section mining. Sources classified `material` must receive explicit coverage accounting and Pass-A raw extraction before semantic reconciliation. No material source can silently disappear from the canonical concept, relation, CQ, mapping, module, or formal-axiom decisions.

## Two-pass method
1. **Pass A — raw extraction:** capture source-native concept-bearing terms, definitions/context, relations, constraints, lifecycle/status semantics, source locators and unresolved ambiguity without premature normalization.
2. **Pass B — semantic disposition:** classify each raw item as already-covered, synonym, narrower, broader, mapping-only, profile/context refinement, Core candidate, CQ/test delta, formalization delta, neighbor-ontology delegation, future work, reject, or unresolved.

## Files
- `SOURCE_REGISTER.csv` — material/source universe and authority/version metadata.
- `SOURCE_COVERAGE.csv` — explicit section/part coverage ledger and blocking status.
- `RAW_SOURCE_CONCEPTS.csv` — source-native extraction surface.
- `SOURCE_RECONCILIATION.csv` — Pass-B semantic disposition and governed-entity trace.

## Current priority
1. EU legal and EUDI ARF/specification lineage, including 2026 amendments.
2. Current global standards/protocols and national trust frameworks.
3. Direct ontology competitors and strongest conceptual models.
4. Neighbor ontologies/vocabularies for explicit reuse/align/bridge decisions.
5. Reconciliation against Gate B, Gate C, DDD, CQs and Draft PR #59 module ownership.

## Claim boundary
The presence of this package does not itself establish source completeness. Source Completeness is attained only when Issue #60/#66 records PASS with no unresolved material-source gap capable of changing the governed semantics or module architecture.
