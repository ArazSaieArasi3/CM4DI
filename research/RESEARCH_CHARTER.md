# CM4DI Journal V2 — Research Charter

## Status
Gate A approved on 2026-08-19. This charter fixes the research mission, journal direction, scope logic, provisional research questions, modular architecture, and decision gates for the journal extension.

## Publication Target
- Primary target: MDPI Information, regular research article.
- Secondary target: MDPI Future Internet.
- Final journal selection and quartile/indexing status will be re-verified immediately before submission.

## Working Mission
Develop CM4DI from a conference-level conceptual ontology and lightweight OWL artifact into a UFO-grounded, cross-paradigm reference ontology for conceptual interoperability across digital-identity standards, trust frameworks, identity architectures, and operational IAM ecosystems.

## Core Research Position
CM4DI is not an SSI-only ontology, a vendor ontology, or an implementation model for a single protocol. Its central contribution is a protocol-agnostic semantic backbone capable of explaining and aligning identity constructs across centralized, federated, enterprise IAM, credential/wallet-based, decentralized, governmental, workload/device, and emerging agent-identity ecosystems.

## Provisional Research Questions
- RQ1: What ontological distinctions are required to represent digital identity consistently across centralized, federated, credential-based, decentralized, governmental, and non-human identity ecosystems?
- RQ2: How can heterogeneous standards, trust frameworks, and operational IAM platforms be semantically aligned without embedding protocol- or vendor-specific constructs into the ontology core?
- RQ3: To what extent does CM4DI provide semantic coverage across representative identity standards and operational ecosystems?
- RQ4: Can the resulting ontology support consistent reasoning, competency-question answering, and cross-ecosystem scenario representation while remaining logically coherent and modular?

## Planned Architecture
### Stable Core
The core should contain only ontologically stable constructs needed across multiple paradigms. Candidate families include identity-bearing entities, digital identity, identifiers, identity context, attributes, claims, credentials, evidence/proof, enrollment/binding, authentication, authorization, assurance, trust, and lifecycle primitives.

### Profile 1 — Enterprise and Federated Identity
Candidate coverage includes OIDC, OAuth, SAML, SCIM, policy/access-control standards where identity-relevant, and representative platforms such as AWS, Microsoft Entra, Google Identity/IAM, Keycloak, Okta/Auth0, Ping, ZITADEL, Ory, and related systems.

### Profile 2 — Wallet and Verifiable Digital Credentials
Candidate coverage includes W3C Verifiable Credentials, DIDs, issuer-holder-verifier patterns, wallet concepts, presentation, OpenID4VC families, SD-JWT VC where relevant, and EUDI Wallet.

### Profile 3 — Machine, Workload, Device, and Agent Identity
Candidate coverage includes workload identities, service principals/accounts, device identity, SPIFFE/SPIRE, workload federation, and emerging AI-agent identity constructs.

### Profile 4 — Trust, Assurance, and Government Identity
Candidate coverage includes ISO identity-management standards, NIST digital-identity guidance, EUDI/eIDAS, UK trust frameworks, Canadian PCTF, Australian digital-ID frameworks, MOSIP, ID4D, and other representative public-sector identity ecosystems.

## Evidence Strategy
Use a bounded structured evidence review rather than an oversized systematic literature review. Evidence is organized into three streams:
1. Academic evidence: peer-reviewed papers, high-quality reviews, and directly competing ontologies/models.
2. Normative evidence: ISO/IEC, NIST, W3C, IETF, OASIS, OpenID Foundation, FIDO, European and national trust frameworks.
3. Operational evidence: cloud IAM platforms, open-source IAM implementations, reference implementations, datasets, and real-world identity architectures.

Discovery is intentionally broader than the final ontology scope. Admission to CM4DI Core requires evidence of conceptual stability and relevance across more than one ecosystem unless a strong ontological argument justifies otherwise.

## Social Identity Boundary
Social login remains in CM4DI discovery because it is an authentication/federation mechanism. Social identity in the sociological sense—social roles, group identity, collective identity, persona, affiliation, attributed identity, reputation, and related constructs—is maintained in a separate discovery track. Such concepts are not automatically admitted to CM4DI Core and may support a future independent social-identity ontology.

## Methodological Direction
The journal extension follows a design-science and ontology-engineering trajectory:
1. Structured multi-source evidence synthesis.
2. Ontology requirements and competency questions.
3. UFO/OntoUML conceptual analysis.
4. Modular ontology engineering.
5. Standard, trust-framework, and operational-platform profile mapping.
6. OWL/SHACL operationalization and synchronized machine-readable artifacts.
7. Multi-layer evaluation through reasoning, CQs, mapping coverage, cross-paradigm scenarios, datasets, reproducibility, and expert assessment where feasible.

OGCM-RF is used as the repository-governance and reproducibility framework, not as the scientific research method itself. Concepts and workflow ideas from the unpublished conceptualization-ontology research may inform internal design, but the journal method must stand independently on published and citable foundations unless that work becomes formally citable before submission.

## Explicit Non-Scope
CM4DI will not become a complete cybersecurity ontology, legal/privacy ontology, biometric ontology, blockchain ontology, or product-specific cloud model. Heavy access-control policy, deep privacy-law semantics, detailed cryptographic mechanisms, and vendor-specific configuration remain profile-level or out of scope unless necessary to explain identity semantics.

## Evaluation Families
- Formal syntax and serialization validation.
- Logical consistency and reasoner checks.
- UFO/OntoUML grounding and anti-pattern review.
- Competency-question and SPARQL evaluation.
- Standards and framework coverage.
- Enterprise/federated IAM mapping.
- Wallet/VC/EUDI mapping.
- Workload/device/agent mapping.
- Cross-paradigm semantic comparison.
- Dataset-based instantiation and scenario validation.
- Reproducibility and release traceability.
- Expert assessment if feasible and methodologically justified.

## Decision Gates
- Gate A — Research Mission: approved. Journal direction, mission, broad scope, profile architecture, and provisional RQs are fixed.
- Gate B — Evidence and Scope Lock: after discovery and evidence grading, decide what enters Core, Profiles, Deferred, or Social-Identity Future Work.
- Gate C — Conceptual Model Freeze: approve the revised UFO/OntoUML conceptual model before major OWL refactoring.
- Gate D — Evaluation Design Lock: freeze scenarios, datasets, mappings, CQs, and expert-evaluation plan.
- Gate E — Submission Lock: approve final manuscript, reproducible release, archived artifacts, and journal submission package.

## Gate A Exit Criteria
Gate A is complete when this charter, the repository implementation profile, and the journal-v2 roadmap exist and the discovery backlog is represented in GitHub Issues.
