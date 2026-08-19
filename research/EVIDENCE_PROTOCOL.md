# CM4DI Journal V2 — Evidence Discovery and Synthesis Protocol

## Purpose
This protocol governs discovery, selection, extraction, grading, provenance, and synthesis of evidence used to evolve CM4DI. It is deliberately bounded: the goal is not to maximize literature volume, but to obtain sufficient high-quality evidence across academic, normative, operational, and empirical sources to justify ontology decisions and evaluate cross-paradigm coverage.

## Evidence Streams
### A. Academic
Peer-reviewed journal and conference papers, high-quality reviews, ontology papers, conceptual models, IAM/federation research, SSI/VC research, trust/assurance research, and relevant machine-identity work.

### B. Normative and Institutional
ISO/IEC, NIST, W3C, IETF, OASIS, OpenID Foundation, FIDO Alliance, European Union/EUDI/eIDAS material, national trust frameworks, and authoritative public digital-identity programs.

### C. Operational and Implementation
Official documentation and reference implementations for representative enterprise/cloud IAM, open-source IAM, wallet/credential systems, workload identity, device identity, and emerging agent identity.

### D. Data and Evaluation
Authentication/identity datasets, public digital-ID datasets, test suites, conformance suites, synthetic-but-provenanced datasets, and machine-readable examples suitable for instantiation or evaluation.

## Discovery Scope
Evidence discovery must cover at least:
- digital identity foundations and identity-management terminology;
- identity proofing, enrollment and binding;
- identifiers, attributes, claims and credentials;
- authentication, authenticators, sessions and assurance;
- authorization and identity-relevant policy constructs;
- federation, SSO, provisioning and identity lifecycle;
- verifiable credentials, wallets, presentations and decentralized identifiers;
- trust frameworks and trust/assurance structures;
- centralized, federated, wallet/VC, decentralized and governmental identity ecosystems;
- human, organizational, workload, device and emerging agent identity;
- representative cloud IAM and open-source IAM products;
- directly competing ontologies and conceptual models;
- datasets and test suites that can support evaluation.

## Inclusion Criteria
A source is included in the curated evidence registry when it satisfies one or more of the following and passes basic provenance checks:
1. It is normative or authoritative for a major identity standard/framework.
2. It is a peer-reviewed source with direct conceptual relevance to digital identity/IAM/trust/assurance.
3. It is official documentation for a representative operational IAM or identity platform.
4. It is an official or well-maintained reference implementation/test suite that exposes identity concepts or lifecycle structures.
5. It is a dataset with clear provenance, access conditions and sufficient semantic relevance for identity evaluation.
6. It provides a competing ontology/model that must be compared for novelty or coverage.

## Exclusion Criteria
Exclude or demote sources that are:
- generic cybersecurity material without identity-specific semantic value;
- marketing-only pages when authoritative technical documentation exists;
- duplicated or superseded specifications unless historically needed;
- unverifiable secondary summaries used in place of primary sources;
- vendor-specific configuration detail with no conceptual relevance;
- social-identity material unrelated to digital identity, unless routed to the separate social-identity opportunity track;
- datasets with unclear provenance or unusable access/licensing when better alternatives exist.

## Source Priority
Priority order within each claim family:
1. current normative/primary specification;
2. official institutional/technical documentation;
3. peer-reviewed primary research;
4. high-quality peer-reviewed reviews;
5. maintained reference implementations/test suites;
6. secondary explanatory material only when necessary.

## Evidence-Grading Dimensions
Each evidence item should be graded independently on:
- Authority: normative / official / peer-reviewed / community / secondary.
- Recency: current / active but older / superseded / historical.
- Directness: directly defines the concept / operationalizes it / discusses it / peripheral.
- Cross-ecosystem relevance: high / medium / low.
- Ontology utility: core candidate / profile candidate / mapping-only / evaluation-only / context-only.
- Reproducibility utility: executable/testable / machine-readable / narrative-only.
- Licensing/access: open / accessible with restrictions / unavailable / uncertain.

No single aggregate score is required; dimensions remain visible to avoid hiding trade-offs.

## Extraction Fields
For each evidence item capture:
- evidence_id;
- title;
- source_family;
- source_type;
- organization_or_authors;
- publication_or_version_date;
- version_or_status;
- persistent_identifier_or_url;
- doi_if_any;
- license_or_access_status;
- paradigm;
- identity_subject_types;
- concept_candidates;
- relation_candidates;
- lifecycle_candidates;
- trust_or_assurance_candidates;
- profile_destination;
- core_relevance;
- mapping_relevance;
- evaluation_relevance;
- social_identity_flag;
- evidence_grade_notes;
- extracted_claim_or_definition_summary;
- provenance_notes;
- supersedes_or_superseded_by;
- review_status.

## Core Admission Rule
A vendor/protocol/framework concept does not enter CM4DI Core merely because it is important in one ecosystem. Core admission normally requires:
- conceptual stability;
- clear ontological interpretation;
- relevance across multiple ecosystems or a strong foundational argument;
- compatibility with UFO/OntoUML distinctions;
- demonstrable support for at least one competency question or cross-paradigm mapping need.

Otherwise the concept is assigned to a profile, mapping layer, deferred register, or excluded.

## Social-Identity Routing Rule
Material concerning social roles, collective identity, persona, social-group membership, self-identification, attributed identity, reputation, or sociological identity must be tagged for the separate social-identity track unless it directly supports a digital-identity construct. Social login is not routed out merely because it contains the word social; it remains an IAM/federation mechanism.

## Discovery Saturation Rule
Discovery for a topic can be considered sufficient when:
- the dominant normative sources are represented;
- at least the major competing academic viewpoints/models are represented;
- representative operational ecosystems are covered;
- new sources mostly repeat already captured concepts/relations rather than adding materially new ontology candidates;
- unresolved contradictions are explicitly logged.

## Synthesis Outputs Before Gate B
- curated evidence registry;
- standards and framework inventory;
- competitor ontology/model matrix;
- operational IAM/platform matrix;
- reference-implementation registry;
- dataset registry;
- concept and relation candidate register;
- contradiction/ambiguity register;
- social-identity opportunity register;
- Core/Profile/Deferred/Reject recommendations with evidence traceability.

## Change Control
Before Gate B, ontology changes are exploratory only. The existing CM4DI OWL and conceptual model remain the baseline. Evidence may generate candidate concepts and relations, but admission decisions are made at Gate B and conceptual formalization proceeds after that decision.
