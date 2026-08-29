# CM4DI — Journal Extension Research

CM4DI is an ongoing research program for a **UFO-grounded, cross-paradigm digital-identity reference ontology**. This `journal-v2` branch develops the substantial journal extension of the published ICWR 2026 conference paper **“An Ontology-Driven Conceptual Model for Digital Identity with Trust Integration”** (DOI: `10.1109/ICWR69602.2026.11513313`).

> **Important:** the root conference OWL and Generation2 diagram are preserved as historical PUB-002 baseline artifacts. They are **not** the authoritative semantic source for journal-v2.

## Current research identity
- Araz Research Portfolio: **R-015 / P1-L6 — Cross-Domain Foundational Semantics**
- Bridges: P3, P5
- Published precursor: **PUB-002**
- Active journal extension: **PUB-003**
- Current stage: **W6.5 — Retrospective Source Completeness Reconciliation**
- Next gate: **OGCM-RF Source Completeness Gate**, then Wave-7 formal module approval and OWL/SHACL implementation.

Machine-readable state:
- `.research/manifest.yaml`
- `.research/ogcm-rf-profile.yaml`
- `.research/semantic-ci-policy.yaml`

## Scientific objective
The journal extension aims to provide one coherent semantic integration layer across:
- human and non-human digital identity;
- enterprise IAM and federation;
- credentials, wallets and verifiable presentations;
- workload, device and AI-agent identity;
- government/legal identity and trust governance;
- authentication and authorization;
- current identity standards, protocols and regulatory/trust frameworks;
- mature neighboring ontologies that should be reused or aligned rather than duplicated.

The project does **not** claim to be the first digital-identity ontology or the first UFO-grounded identity ontology. Claims such as `complete`, `comprehensive`, `integrated`, `interoperable`, `reference ontology` and `validated` are evaluation-dependent and governed by PUB-003 MQAP-EXT work.

## Current governed semantic state
- **102 governed concepts**: 34 frozen Core + 68 extension/profile concepts.
- **120 governed relations**: 55 frozen Core + 65 extension/profile relations.
- **52 Competency Questions**: 32 Core + 20 profile/context CQs.
- **68 external/profile mappings**.
- **15 DDD subdomains** and **13 Bounded Contexts**.
- **4 cross-domain integration Profiles**.
- Gate B approved; Gate C approved and retained after DDD regression.
- DDD regression Issues #50–#57: PASS.

### DDD architecture
Overall Domain: **Digital Identity Management**.

Canonical subdomains:
1. Identity Representation
2. Identity Information
3. Identity Evidence
4. Identity Establishment
5. Credential Management
6. Authentication
7. Authorization
8. Identity Administration
9. Federation
10. Credential Exchange
11. Workload Identity
12. Device Identity
13. Agent Identity
14. Trust Governance
15. Government Identity

Governance invariant:

`Domain != Bounded Context != Profile != OWL Module`

Canonical Domain and Bounded Context names do not use `and`, `&`, or slash-composed semantic centers.

### Cross-domain Profiles
- **P01 Enterprise Identity Profile**
- **P02 Verifiable Credential Profile**
- **P03 Technical Identity Profile**
- **P04 Governed Identity Profile**

Profiles are integration views; they do not own DDD meaning and do not automatically define OWL module boundaries.

## Gate-C conceptual source of truth
Start here for current conceptual semantics:
- `model/journal-v2/CM4DI_CORE_CONCEPT_REGISTRY_v2.csv`
- `model/journal-v2/CM4DI_CORE_RELATION_REGISTRY_GATE_C.csv`
- `model/journal-v2/CM4DI_CORE_CONCEPTUAL_MODEL_v2.mmd`
- `model/journal-v2/ddd/DOMAIN_REGISTRY_v2.csv`
- `model/journal-v2/ddd/BOUNDED_CONTEXT_REGISTRY_v2.csv`
- `model/journal-v2/ddd/CONCEPT_DOMAIN_ASSIGNMENT_v2.csv`
- `model/journal-v2/ddd/CONTEXT_MAP_v2.md`
- `model/journal-v2/profiles/PROFILE_CONCEPT_REGISTRY_v2.csv`
- `model/journal-v2/profiles/PROFILE_RELATION_REGISTRY_v2.csv`

The old conference README stereotypes and actor hierarchy are historical and superseded for journal-v2. In particular, journal-v2 does **not** model `Party` as a universal rigid kind or `IdentitySubject` as a rigid subkind; the Gate-C registry governs their current UFO interpretation.

## Evidence and Source Completeness
The original discovery program produced **134 curated evidence records** spanning normative standards, government/trust frameworks, enterprise IAM, non-human identity, implementations/datasets, scholarship and Social Identity boundary work.

Current OGCM-RF requires a stronger **Exhaustive Source Mining** discipline before formal module/axiom freeze. The retrospective program is Issue #60 and uses:
- `conceptualization/source-mining/SOURCE_REGISTER.csv`
- `conceptualization/source-mining/SOURCE_COVERAGE.csv`
- `conceptualization/source-mining/RAW_SOURCE_CONCEPTS.csv`
- `conceptualization/source-mining/SOURCE_RECONCILIATION.csv`

Priority sources include current EU/EUDI law and ARF, ISO/NIST/W3C/OpenID/IETF/OASIS/FIDO, global trust frameworks, direct ontology competitors and neighboring ontologies.

Reviewer-facing tables live in `evidence/catalogs/` and separate:
- standards;
- protocol specifications;
- EU regulatory/EUDI frameworks;
- global trust frameworks;
- direct competing ontologies;
- broader academic competitors;
- neighboring ontologies.

## European Digital Identity focus
The journal program explicitly tracks:
- Regulation (EU) 2024/1183;
- EUDI Wallet Architecture and Reference Framework, current stable lineage;
- wallet implementing regulations for PID/EAA, wallet integrity/core functionality, ecosystem notifications, certification, protocols/interfaces and relying-party registration;
- 2026 amendment/consolidation lineage;
- wallet actors, PID/EAA, relying-party registration/intended use, trust lists/anchors, certification and functional conformance.

EU legal/technical concepts are mapped into CM4DI Domains/Contexts/Profiles; they do not automatically become Core ontology concepts.

## Competing and neighboring ontologies
Direct/near-direct ontology comparison currently includes MFSSIA 2026, Layouni and Pollet 2009 federated-identity OWL work, Nahar 2021 IAM ontology/metamodel and other qualified formal/conceptual identity models. Broader current work includes Comb and Martin 2026 and current SSI/interoperability frameworks.

Neighbor-ontology candidates currently include:
- UFO / gUFO;
- ONTrust;
- PROV-O;
- W3C Organization Ontology;
- ODRL;
- Data Privacy Vocabulary;
- W3C VC/RDF vocabularies and additional qualified security/IAM ontologies.

The intended role of CM4DI is **semantic integration**: identity-specific concepts remain governed in CM4DI, while mature generic trust, provenance, organization, privacy and policy semantics are reused/aligned/bridged where justified.

## Wave-7 formal ontology status
Issue #58 / Draft PR #59 contain a structurally validated **12-module engineering candidate** plus four non-owning aggregate Profile entrypoints.

Current structural checks: 102/102 concept ownership, 120/120 relation ownership, no duplicates/orphans, no import cycles and no Core→extension imports.

The PR intentionally remains **Draft and not frozen** until Source Completeness #60/#66 passes. After approval, Issue #69 defines formal UFO/gUFO-to-OWL projection and OWL-vs-SHACL constraint allocation before reasoner evaluation begins.

No journal-v2 HermiT/ROBOT/SHACL/SPARQL formal PASS is currently claimed.

## Journal plan
PUB-003 is governed by:
- `research/JOURNAL_RESEARCH_CONTRACT_2026-08-29.md`
- `publications/PUB002_TO_PUB003_EXTENSION_DELTA.md`
- Issue #67 — ARP::MQAP-EXT research/contribution lock.

The manuscript must demonstrate substantive conference-to-journal delta through source completeness, stronger formal ontology engineering, standards/EU/framework integration, neighbor-ontology alignment, direct-competitor benchmarking and reproducible multi-layer evaluation.

## Current execution order
1. Complete #61 source universe/coverage.
2. Execute #62 EU/EUDI, #63 standards/frameworks, #64 competitors and #65 neighbors.
3. Complete #68 reviewer-facing catalogs.
4. Reconcile sources and rerun semantic/module regression in #66.
5. Pass #60 Source Completeness Gate.
6. Confirm/amend and approve #58/#59 module architecture.
7. Execute #69 formal ontology commitments and subsequent OWL/SHACL/CI/CQ work.
8. Gate D → Wave 8 evaluation → PUB-003 manuscript/release → Gate E.

## Historical conference artifacts
The following root files are retained for publication lineage and regression comparison:
- `CM4DI.owl`
- `CM4DI-Generation2-Version15.drawio`
- `CM4DI-Generation2-Version15.jpg`
- `CM4DI-field-registry-v0.1.md`
- `case-study-pharmaceutical-ecosystem.md`

Do not infer current journal-v2 conceptual semantics from these files unless a current mapping/decision artifact explicitly says so.

## License
Apache License 2.0; see `LICENSE`.
