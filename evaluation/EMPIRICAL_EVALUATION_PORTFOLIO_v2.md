# CM4DI Empirical Evaluation Portfolio v2

Status: **candidate Gate-D input; dataset qualification in progress under Issue #74**.

## Evaluation principle
No single dataset can validate a cross-paradigm digital-identity ontology. The empirical portfolio therefore uses complementary datasets to test representational capacity, instantiation, competency questions, temporal/event semantics and profile coverage. Normative adequacy and ontological validity remain separate evaluation layers.

## Primary portfolio

### 1. LANL User-Computer Authentication Associations in Time — CM4DI-DS0001
- Persistent identifier: https://doi.org/10.11578/1160076
- Role: large-scale authentication graph and temporal event evaluation.
- CM4DI focus: Authentication, AuthenticationResult proxy, Account/user representation, computer/device association.
- Strength: very large authentic event corpus; deterministic slicing possible.
- Limitation: successful authentication only; no explicit credential/session/authorization semantics.

### 2. Risk-Based Authentication Login Dataset — CM4DI-DS0002
- Persistent identifier: https://doi.org/10.5281/zenodo.6782156
- Role: authentication attempt/outcome/context scenarios.
- CM4DI focus: Authentication, AuthenticationResult, Account, device/client context and contextual risk observations.
- Strength: >33M attempts and >3.3M users; success/failure and contextual fields.
- Limitation: feature values are synthetic while preserving selected real distributions/relations; not production-security ground truth.

### 3. World Bank ID4D Global Dataset 2025 — CM4DI-DS0003
- Canonical source: https://id4d.worldbank.org/global-dataset
- Role: government/digital-ID system and capability context.
- CM4DI focus: Government Identity, Trust Governance, LegalIdentity, digital credential and remote-authentication capability.
- Strength: international cross-country coverage.
- Limitation: aggregate/system level; not transaction/event data and not ontology authority.

### 4. LANL Comprehensive Multi-Source Cyber-Security Events — CM4DI-DS0005
- Canonical source: https://csr.lanl.gov/data/cyber1/
- Role: candidate richer enterprise-authentication evaluation using identity-relevant slices only.
- CM4DI focus: Authentication success/failure, account/user representation, computer/device, source/destination context, AD/controller context and selected compromise scenarios.
- Strength: 58 days, 1.6B+ multi-source events with explicit authentication success/failure.
- Limitation: broad cybersecurity corpus; identity evaluation must use a bounded projection and must not infer ontology semantics from process/network columns.

## Secondary complement

### Global Findex Database 2025 with ID4D module — CM4DI-DS0004
- DOI: https://doi.org/10.48529/bk9n-8r43
- Role: person-level ownership/use examples complementing ID4D supply-side/system data.
- Limitation: survey/self-report semantics; cannot establish technical assurance.

## Monitor/excluded datasets

- **CM4DI-DS0006 Behavior-based User Authentication Dataset** — excluded from primary portfolio because file access is restricted and the scope is narrow behavioral authentication.
- **CM4DI-DS0007 Pre-AttentiveGaze** — monitor for optional authenticator-modality diversity; high-quality recent data but too narrow to justify a primary identity-ontology role.

## Planned empirical tests

| Evaluation family | Dataset(s) | Example capability |
|---|---|---|
| Authentication event instantiation | DS0001, DS0002, DS0005 | instantiate Authentication separately from subject/account/device representations |
| Result/context distinction | DS0002, DS0005 | distinguish AuthenticationResult from contextual observations and Session |
| Temporal/event scalability | DS0001, DS0005 | query very large event graphs/samples without changing ontology design |
| Device/computer representation | DS0001, DS0002, DS0005 | test Device versus managed account/user/client observations |
| Government identity context | DS0003, DS0004 | model legal/digital-ID availability and use without claiming individual transaction semantics |
| Cross-dataset semantic normalization | DS0001, DS0002, DS0005 | map heterogeneous authentication schemas to one CM4DI vocabulary |

## Reproducibility requirements

1. Raw multi-GB datasets are not committed.
2. Store persistent IDs, official source links, checksums for downloaded inputs where feasible, and exact retrieval dates.
3. Use deterministic sampling scripts and document filters/seeds.
4. Preserve source-column → CM4DI mapping tables.
5. Never silently transform a dataset label into a canonical ontology class.
6. Derived samples must preserve licensing and privacy constraints.
7. Evaluation results must bind to ontology/model version and commit SHA.
8. Report limitations separately for source realism, semantic coverage and technical scale.

## Gate-D recommendation
Use DS0001 + DS0002 + DS0003 as the minimum complementary empirical set. Add DS0005 if the bounded extraction remains operationally manageable and provides meaningful failure/context scenarios beyond DS0002. Keep DS0004 as a secondary government-ID complement.

This portfolio is not frozen until Gate D.