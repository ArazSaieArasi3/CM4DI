# CM4DI — Digital Identity Reference Ontology Research

CM4DI is the governed research locus for **R-015 — Digital Identity Ontology / Conceptual Model**. The active `journal-v2` branch develops a substantial journal extension of the published ICWR 2026 paper **“An Ontology-Driven Conceptual Model for Digital Identity with Trust Integration”** (DOI: `10.1109/ICWR69602.2026.11513313`).

The research objective is a **UFO-grounded, cross-paradigm digital-identity reference ontology** that connects digital-identity standards, regulatory/trust frameworks, operational IAM ecosystems and neighboring ontologies through one coherent semantic layer.

> **Version rule:** the published v1 artifacts remain stable and directly accessible. The journal-v2 research supersedes them only for ongoing semantics; it does not rewrite the scholarly baseline.

## Quick navigation

| Research surface | Starting point |
|---|---|
| Published conference baseline | [`versions/v1-published/README.md`](versions/v1-published/README.md) |
| Active journal extension | [`versions/v2-journal/README.md`](versions/v2-journal/README.md) |
| Version lineage | [`versions/README.md`](versions/README.md) |
| Current state and next gate | [`STATUS.md`](STATUS.md) |
| Journal-v2 roadmap | [`roadmap/JOURNAL_V2_ROADMAP.md`](roadmap/JOURNAL_V2_ROADMAP.md) |
| Current Core concepts | [`model/journal-v2/CM4DI_CORE_CONCEPT_REGISTRY_v2.csv`](model/journal-v2/CM4DI_CORE_CONCEPT_REGISTRY_v2.csv) |
| Current Core relations | [`model/journal-v2/CM4DI_CORE_RELATION_REGISTRY_GATE_C.csv`](model/journal-v2/CM4DI_CORE_RELATION_REGISTRY_GATE_C.csv) |
| DDD domains and contexts | [`model/journal-v2/ddd/`](model/journal-v2/ddd/) |
| Standards, frameworks and ontology catalogs | [`evidence/catalogs/`](evidence/catalogs/) |
| Source Completeness work | [`conceptualization/source-mining/`](conceptualization/source-mining/) |
| Journal research contract | [`research/JOURNAL_RESEARCH_CONTRACT_2026-08-29.md`](research/JOURNAL_RESEARCH_CONTRACT_2026-08-29.md) |
| Current ontology-engineering program | GitHub Issues `#58–#70` |
| Repository orientation | [`READING-GUIDE.md`](READING-GUIDE.md) |
| Artifact map | [`INDEX.md`](INDEX.md) |

## Version map

| Version line | Scholarly role | Status | Semantic interpretation |
|---|---|---|---|
| **v1 / PUB-002** | ICWR 2026 published conference baseline | Published | Historical/published source for the conference contribution |
| **v2 / PUB-003** | Substantial journal extension | Active research | Current governed semantic program after Gate B, Gate C and DDD alignment |

The original root files remain at their established paths so prior citations and links continue to resolve:

- `CM4DI.owl`
- `CM4DI-Generation2-Version15.drawio`
- `CM4DI-Generation2-Version15.jpg`
- `CM4DI-field-registry-v0.1.md`
- `case-study-pharmaceutical-ecosystem.md`

Those files are **not** the authoritative journal-v2 semantic source unless a current mapping or decision artifact explicitly says so.

## Research identity

- **Research:** `R-015 — CM4DI`
- **Primary Program:** `P1 — Foundational Ontology and Conceptualization`
- **Research Line:** `P1-L6 — Cross-Domain Foundational Semantics`
- **Cross-Program Bridges:** `P3`, `P5`
- **Published precursor:** `PUB-002`
- **Active journal extension:** `PUB-003`
- **Current stage:** `W6.5 — Retrospective Source Completeness Reconciliation`
- **Next gate:** OGCM-RF Source Completeness Gate → formal module approval → formal ontology implementation

The canonical Araz Research Portfolio remains a **private governance repository**. CM4DI exposes its public research identity locally so reviewers and external readers do not depend on private Portfolio access. A separate public-facing Portfolio index is a planned future initiative and is not required for CM4DI navigation today.

Machine-readable state:

- `.research/manifest.yaml`
- `.research/ogcm-rf-profile.yaml`
- `.research/semantic-ci-policy.yaml`

## Scientific objective

The journal extension aims to integrate semantics across:

- human and non-human digital identity;
- enterprise IAM and federation;
- credentials, wallets and verifiable presentations;
- workload, device and AI-agent identity;
- government/legal identity and trust governance;
- identity proofing and enrollment;
- authentication and authorization;
- current standards, protocols and regulatory frameworks;
- operational implementations and representative datasets;
- mature neighboring ontologies that should be reused, aligned or bridged rather than duplicated.

The project does **not** claim to be the first digital-identity ontology or the first UFO-grounded identity ontology. Terms such as `complete`, `comprehensive`, `integrated`, `interoperable`, `reference ontology` and `validated` remain evaluation-dependent claims governed by PUB-003 MQAP-EXT work.

## Current governed semantic state

- **102 governed concepts**: 34 frozen Core + 68 extension/profile concepts.
- **120 governed relations**: 55 frozen Core + 65 extension/profile relations.
- **52 Competency Questions**: 32 Core + 20 profile/context CQs.
- **68 governed external/profile mappings**.
- **15 DDD subdomains** and **13 Bounded Contexts**.
- **4 cross-domain integration Profiles**.
- Gate B approved.
- Gate C approved and retained after the DDD regression audit.
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

Profiles are integration views; they do not automatically define OWL module boundaries.

## Current conceptual source of truth

The Gate-C journal-v2 conceptual baseline is governed by:

- `model/journal-v2/CM4DI_CORE_CONCEPT_REGISTRY_v2.csv`
- `model/journal-v2/CM4DI_CORE_RELATION_REGISTRY_GATE_C.csv`
- `model/journal-v2/CM4DI_CORE_CONCEPTUAL_MODEL_v2.mmd`
- `model/journal-v2/ddd/DOMAIN_REGISTRY_v2.csv`
- `model/journal-v2/ddd/BOUNDED_CONTEXT_REGISTRY_v2.csv`
- `model/journal-v2/ddd/CONCEPT_DOMAIN_ASSIGNMENT_v2.csv`
- `model/journal-v2/ddd/CONTEXT_MAP_v2.md`
- `model/journal-v2/profiles/PROFILE_CONCEPT_REGISTRY_v2.csv`
- `model/journal-v2/profiles/PROFILE_RELATION_REGISTRY_v2.csv`

The old conference stereotypes and actor hierarchy are historical for journal-v2. In particular, current semantics do not treat `Party` as a universal rigid kind or `IdentitySubject` as a rigid subkind.

## Evidence and Source Completeness

The original discovery program produced **134 curated evidence records** across normative standards, government/trust frameworks, enterprise IAM, non-human identity, implementations/datasets, academic literature and Social Identity boundary research.

Current OGCM-RF adds a stricter **Exhaustive Source Mining** requirement before formal module and axiom freeze. The active reconciliation uses:

- `conceptualization/source-mining/SOURCE_REGISTER.csv`
- `conceptualization/source-mining/SOURCE_COVERAGE.csv`
- `conceptualization/source-mining/RAW_SOURCE_CONCEPTS.csv`
- `conceptualization/source-mining/SOURCE_RECONCILIATION.csv`

Reviewer-facing catalogs in `evidence/catalogs/` separate:

- standards;
- protocol specifications;
- EU regulatory/EUDI frameworks;
- global trust frameworks;
- direct competing ontologies;
- broader academic competitors;
- neighboring ontologies.

## European Digital Identity focus

The journal program explicitly tracks current European material including:

- Regulation (EU) 2024/1183;
- EUDI Wallet Architecture and Reference Framework current stable lineage;
- wallet implementing regulations for PID/EAA, wallet integrity/core functionality, ecosystem notifications, certification, protocols/interfaces and relying-party registration;
- 2026 amendment and consolidation lineage;
- wallet actors, PID/EAA, relying-party registration and intended use;
- trust lists, trust anchors, certification and functional conformance.

EU legal/technical constructs are mapped into CM4DI Domains, Bounded Contexts and Profiles; they do not automatically become Core ontology concepts.

## Competing and neighboring ontologies

Direct or near-direct comparison includes MFSSIA 2026, Layouni and Pollet 2009 federated-identity OWL work, Nahar 2021 IAM ontology/metamodel and other qualified formal or conceptual identity models. Broader current work includes Comb and Martin 2026 and recent SSI/interoperability frameworks.

Neighbor-ontology candidates include:

- UFO / gUFO;
- ONTrust;
- PROV-O;
- W3C Organization Ontology;
- ODRL;
- Data Privacy Vocabulary;
- W3C VC/RDF vocabularies;
- additional qualified security/IAM ontologies.

CM4DI's intended role is **semantic integration**. Identity-specific semantics remain governed in CM4DI while mature generic trust, provenance, organization, privacy and policy semantics are reused, aligned or bridged where justified.

## Adjacent research ecosystem

CM4DI participates in a wider semantic research ecosystem without collapsing neighboring Researches into one ontology.

| Research | Relationship to CM4DI | Ownership boundary |
|---|---|---|
| **SemSocialIdentity — R-031** | Adjacent Social Identity ontology research | Social identity, persona, role identity, affiliation, collective identity, reputation and related social-context phenomena; repository currently private during governed bootstrap |
| **Commentium — R-003** | Discourse/comment use cases can consume identity bridges | Comment/discourse events, participants, interpretation, expression and interaction semantics remain Commentium-owned |
| **Newsium — R-004** | News actors, authors, sources and affiliation can consume identity bridges | News/information semantics remain Newsium-owned |

Key boundary:

`Social Identity != Digital Identity`

`SocialLogin` remains a CM4DI federation/authentication mechanism, not a Social Identity concept. SemSocialIdentity is a **separate Research**, not a CM4DI module. Cross-research mappings must remain explicit, conservative and regression-tested.

Public repositories:

- [Commentium](https://github.com/ArazSaieArasi3/Commentium)
- [Newsium](https://github.com/ArazSaieArasi3/Newsium)

SemSocialIdentity stays private during its current bootstrap; its public-visibility decision is deferred.

## Wave-7 formal ontology status

Issue #58 / Draft PR #59 contain a structurally validated **12-module engineering candidate** plus four non-owning aggregate Profile entrypoints.

Current structural checks:

- 102/102 concept ownership;
- 120/120 relation ownership;
- no duplicates or orphans;
- no import cycles;
- no Core→extension imports.

The PR remains intentionally **Draft and not frozen** until Source Completeness #60/#66 passes. After approval, Issue #69 governs UFO/gUFO-to-OWL projection and OWL-vs-SHACL constraint allocation before reasoner evidence is claimed.

No journal-v2 HermiT, ROBOT, SHACL or SPARQL formal PASS is currently claimed.

## Journal program

PUB-003 is governed by:

- `research/JOURNAL_RESEARCH_CONTRACT_2026-08-29.md`
- `publications/PUB002_TO_PUB003_EXTENSION_DELTA.md`
- Issue #67 — ARP::MQAP-EXT research/contribution lock.

The manuscript must demonstrate substantive conference-to-journal delta through Source Completeness, stronger formal ontology engineering, standards/EU/framework integration, neighbor-ontology alignment, direct-competitor benchmarking and reproducible multi-layer evaluation.

**Venue selection is intentionally deferred.** The working strategy is to build at Q1-level research quality independent of the final journal choice; speed remains an important later decision criterion.

## Current execution order

1. Complete #61 source universe and coverage.
2. Execute #62 EU/EUDI, #63 standards/frameworks, #64 competitors and #65 neighbors.
3. Complete #68 reviewer-facing catalogs.
4. Reconcile sources and rerun semantic/module regression in #66.
5. Pass #60 Source Completeness Gate.
6. Confirm or amend #58/#59 module architecture.
7. Execute #69 formal ontology commitments and subsequent OWL/SHACL/CI/CQ work.
8. Gate D → Wave 8 evaluation → PUB-003 manuscript/release → Gate E.

## License

Apache License 2.0; see `LICENSE`.
