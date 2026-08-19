# CM4DI Journal V2 — Research and Ontology Roadmap

## Objective
Evolve CM4DI into a publication-ready, reproducible, cross-paradigm reference ontology for digital identity while preserving a stable core and separating ecosystem-specific semantics into profiles.

## Execution Principle
Work proceeds through evidence-first discovery, scope locking, conceptual-model refinement, formalization, mapping, evaluation, and publication. The existing OWL model is not expanded substantially before Gate B and Gate C, reducing ontology churn and rework.

## Wave 0 — Governance and Baseline
- G01 Preserve conference baseline and isolate journal development.
- G02 Audit current repository, ontology, field registry, diagrams, case study, and documentation.
- G03 Adopt OGCM-RF implementation structure progressively.
- G04 Define stable IDs for concepts, relations, evidence, CQs, mappings, datasets, evaluations, and releases.
- G05 Define versioning and release policy.
- G06 Establish structured evidence/provenance registry.
- R01 Fix mission, scope, non-scope, and journal direction.
- R02 Fix provisional research questions.
- R03 Define bounded structured evidence-review protocol.

## Wave 1 — Academic and Ontology Discovery
- D01 Digital-identity literature discovery.
- D02 IAM/federation literature discovery.
- D03 SSI/wallet/verifiable-credential literature discovery.
- D04 Direct competitor ontology and conceptual-model review, including recent UFO-grounded identity work.
- D20 Deduplication, provenance normalization, and evidence grading.

## Wave 2 — Standards and Trust-Framework Discovery
- D05 ISO/IEC identity standards inventory.
- D06 NIST/FIDO inventory.
- D07 W3C/IETF/OASIS/OpenID inventory.
- D08 EUDI/eIDAS inventory and architecture mapping candidates.
- D09 UK, Canadian PCTF, Australian, and comparable national trust frameworks.
- D10 MOSIP, World Bank ID4D, and representative national/public digital-ID ecosystems.

## Wave 3 — Operational IAM and Reference Implementations
- D11 AWS IAM, IAM Identity Center, Cognito, and related identity services.
- D12 Microsoft Entra identity families and architecture.
- D13 Google Identity and IAM families.
- D14 Okta/Auth0, Ping, Keycloak, ZITADEL, Ory, Authentik, and selected alternatives.
- D15 Workload/device identity and SPIFFE/SPIRE.
- D16 Emerging AI-agent identity.
- D17 GitHub reference implementations and test suites.

## Wave 4 — Data and Adjacent Opportunity Discovery
- D18 Identity/authentication/SSO/government-ID datasets, prioritizing DOI/provenance-rich sources.
- D19 Segregated social-identity evidence and future-ontology opportunity registry.
- D20 Cross-source deduplication, provenance, quality and evidence grading.

## Gate B — Evidence and Scope Lock
Outputs required before the decision:
- curated evidence registry;
- standards/framework inventory;
- operational-platform matrix;
- dataset registry;
- competitor/model matrix;
- concept/relation candidate register;
- social-identity future-work register;
- explicit Core/Profile/Deferred/Reject recommendations.

## Wave 5 — Conceptual Model Revision
- O01 Conference-model gap analysis against evidence.
- O02 Competency-question registry.
- O03 Core/Profile boundary formalization.
- O04 Party, IdentitySubject, human and non-human identity review.
- O05 DigitalIdentity, Identifier, IdentityContext review.
- O06 Claim, Credential, Evidence and Proof review.
- O07 Identity proofing, enrollment and binding model.
- O08 Authentication, Authenticator, Session and Assurance model.
- O09 Authorization, Resource, Action, Permission and identity-relevant Policy model.
- O10 Trust framework/reference/anchor/list model.
- O11 Identity lifecycle model.
- O12 Consent/privacy boundary decision.
- O13 Workload/device/agent identity model if evidence warrants inclusion.
- O14 UFO/OntoUML stereotype and foundational-grounding review.
- O15 OntoUML anti-pattern review.
- O16 Freeze CM4DI Core candidate.

## Gate C — Conceptual Model Freeze
The revised OntoUML/UFO model and Core/Profile boundaries are approved before major formal-ontology refactoring.

## Wave 6 — Profiles and Mappings
- P01 Enterprise/Federated Identity Profile.
- P02 Wallet/Verifiable Digital Credential Profile.
- P03 Machine/Workload/Device/Agent Identity Profile.
- P04 Trust/Assurance/Government Identity Profile.

## Wave 7 — Formal Ontology and Automation
- I01 Establish canonical OWL source policy and release candidate.
- I02 SHACL constraints.
- I03 Deterministic serialization pipeline for required RDF/OWL formats.
- I04 Namespace, IRI and version-IRI governance.
- I05 CI validation workflow.
- I06 ROBOT/HermiT logical checks.
- I07 SPARQL competency-question suite.
- I08 Machine-readable example instances and scenarios.
- I09 Documentation generation.
- I10 Machine-readable mapping artifacts.

## Gate D — Evaluation Design Lock
Freeze representative standards, platforms, datasets, scenarios, CQs, metrics, reasoners and expert-review protocol before final evaluation.

## Wave 8 — Evaluation
- E01 Syntax/serialization validation.
- E02 Logical consistency.
- E03 Ontological grounding and anti-pattern evaluation.
- E04 Competency-question evaluation.
- E05 Standards/framework coverage evaluation.
- E06 Enterprise IAM mapping experiment.
- E07 EUDI/VC mapping experiment.
- E08 Workload identity mapping experiment.
- E09 Cross-paradigm interoperability analysis.
- E10 Dataset-based instantiation/mapping.
- E11 Expert assessment if feasible.
- E12 Comparative benchmark against existing ontologies/frameworks.
- E13 Limitations and threats-to-validity analysis.

## Wave 9 — Journal Article and Scholarly Release
- A01 Conference-to-journal extension delta matrix.
- A02 Journal outline.
- A03 Focused Related Work.
- A04 Journal methodology.
- A05 CM4DI Core and profile specification section.
- A06 Mapping/interoperability results.
- A07 Evaluation results.
- A08 Discussion and theoretical/practical implications.
- A09 Reproducibility and data-availability section.
- A10 Conference-overlap audit.
- A11 Rhetorical, terminological and language-quality pass.
- A12 Versioned GitHub release and citable archive/DOI where feasible.
- A13 Submission package for the selected journal.

## Gate E — Submission Lock
Final approval of manuscript, release artifacts, reproducibility package, declarations, references, figures, supplementary material, and target-journal compliance.

## Default Autonomy Rule
Discovery, evidence registration, mapping preparation, documentation, tests, registry maintenance, and non-destructive repository organization are Green work. Work pauses for user decision only at Gates B, C, D and E or when a discovery materially changes the approved mission.
