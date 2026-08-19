# CM4DI Stable Identifiers and Versioning Policy

## Status
Journal-v2 governance policy adopted before evidence-registry population. It follows OGCM-RF principles while preserving existing public CM4DI IRIs.

## 1. Stable Research-Artifact Identifiers
Stable IDs are independent of mutable labels and document versions. Once allocated to a released entity, an ID is never reused for a different entity.

### Prefix
`CM4DI-`

### Entity-Type Codes
- `C` — Concept: `CM4DI-C0001`
- `R` — Relation: `CM4DI-R0001`
- `D` — Domain / bounded view: `CM4DI-D0001`
- `EVID` — Evidence item: `CM4DI-EVID0001`
- `DS` — Dataset: `CM4DI-DS0001`
- `MAP` — Mapping: `CM4DI-MAP0001`
- `CQ` — Competency Question: `CM4DI-CQ0001`
- `EVAL` — Evaluation artifact/run: `CM4DI-EVAL0001`
- `PUB` — Publication: `CM4DI-PUB0001`
- `APP` — Application/consumer: `CM4DI-APP0001`
- `CHG` — Semantic change record: `CM4DI-CHG0001`
- `REL` — Release record: `CM4DI-REL0001`

### Allocation Rules
1. Allocate monotonically within each entity type.
2. IDs never encode preferred labels, standards, vendors, profiles or versions.
3. A rename does not change the stable ID when semantic identity is preserved.
4. Material semantic replacement normally receives a new ID; predecessor/successor lineage must be recorded.
5. Split and merge operations preserve explicit lineage.
6. Retired IDs remain reserved permanently.
7. Discovery candidates may receive provisional registry IDs, but only accepted/released semantic entities are treated as stable ontology entities.

## 2. Ontology IRIs
The existing public base IRI `https://w3id.org/cm4di#` is preserved unless a later technical audit demonstrates a compelling migration requirement.

Research-artifact IDs are governance identifiers and do not automatically replace public OWL IRIs. Any future alignment between stable IDs and ontology IRIs must be deliberate and backward-compatible where possible.

## 3. Versioning Model
CM4DI separates:
- conceptual-model version;
- formal-ontology version;
- documentation version;
- evaluation binding;
- publication binding;
- scholarly release record.

### Semantic Versioning Rule
Use `MAJOR.MINOR.PATCH` according to semantic impact:
- PATCH: documentation, metadata or serialization repair without semantic change.
- MINOR: backward-compatible semantic enrichment.
- MAJOR: central conceptual restructuring, incompatible constraints/cardinalities, changed identity criteria or foundational interpretation.

### Current Historical Baseline
The published conference-era repository state is referenced as the **conference baseline**. No retroactive stable semantic-version number is asserted merely for convenience.

### Journal Development Line
`journal-v2` is a development branch name, not itself a scholarly semantic version. Formal journal-model version assignment occurs after Gate B/Gate C when semantic impact is known. A pre-release identifier may then be used for release candidates.

## 4. Release Immutability
Stable scholarly releases are immutable research objects. Corrections require a new version/release record rather than silent replacement.

Each stable release should eventually include:
- release ID;
- model version;
- ontology version;
- date;
- OGCM-RF framework version/profile;
- registry references/entity membership;
- evaluation status and bound evaluation IDs;
- linked publication(s);
- generated serializations and checksums where feasible.

## 5. Evaluation and Publication Binding
Evaluation findings are valid only for the model/ontology version explicitly evaluated. Journal and future publications must identify the release they report. Results are not silently carried forward after semantic changes.

## 6. Immediate Registry Convention
The first evidence record added during journal-v2 discovery will use `CM4DI-EVID0001`, with subsequent records allocated sequentially. Dataset entries additionally receive `CM4DI-DS####` IDs and mappings receive `CM4DI-MAP####` IDs when created.
