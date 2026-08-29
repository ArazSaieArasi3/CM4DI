# CM4DI External Evidence Catalogs

## Purpose
These tables are reviewer-facing navigation and comparison surfaces over CM4DI's governed evidence and Exhaustive Source Mining records. They do not replace source-level provenance or raw extraction.

## Catalog families
1. `STANDARDS_CATALOG.csv` — normative standards and specifications.
2. `PROTOCOL_SPECIFICATION_CATALOG.csv` — protocol-level specifications where operational mapping matters.
3. `EU_REGULATORY_FRAMEWORK_CATALOG.csv` — EU legal, EUDI architecture, implementing-regulation and conformance sources.
4. `GLOBAL_TRUST_FRAMEWORK_CATALOG.csv` — government/institutional trust frameworks outside the EU and cross-jurisdictional comparators.
5. `COMPETING_ONTOLOGY_CATALOG.csv` — direct or near-direct ontology/formal-model competitors.
6. `ACADEMIC_COMPETITOR_CATALOG.csv` — broader scholarly competitors, conceptual frameworks, surveys and reference models.
7. `NEIGHBOR_ONTOLOGY_CATALOG.csv` — mature adjacent ontologies/vocabularies that CM4DI should reuse, align, bridge or explicitly not import.

## Common interpretation
- **source** — contributes evidence to CM4DI semantic decisions.
- **direct competitor** — makes an ontology/formal-model contribution overlapping CM4DI's scientific claim.
- **neighbor ontology** — owns mature semantics adjacent to CM4DI; integration is preferred over duplication where appropriate.
- **mapping target** — external operational/normative construct mapped to CM4DI without being ontology authority.
- **evaluation source** — supports coverage/conformance/scenario evaluation.

## Status discipline
`coverage_status` is governed by `conceptualization/source-mining/SOURCE_COVERAGE.csv`. A table row can exist before source completeness; `pending` must never be interpreted as verified exhaustive extraction.

## CM4DI positioning
CM4DI is intended as an integrated, UFO-grounded, cross-paradigm digital-identity reference ontology. It does not seek to absorb the entire semantics of trust, provenance, organization, privacy or generic policy. Neighbor ontologies remain independently governed and are connected through explicit mappings/import decisions.
