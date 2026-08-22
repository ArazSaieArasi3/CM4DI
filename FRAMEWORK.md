# Framework Adoption

CM4DI follows **OGCM-RF — Ontology-Grounded Conceptual Model Repository Framework** for its journal-extension research and ontology evolution and uses Domain-Driven Design as a strategic problem-space organization technique where it improves semantic ownership and integration clarity.

**Framework Version:** 0.1.0 development baseline  
**Conformance Status:** Adoption in progress; no formal conformance claim yet.

## Implementation Profile
See `REPOSITORY_PROFILE.yaml`.

## Implemented Capabilities
- UFO-grounded and OntoUML-specified conceptual model with Gate-C semantic freeze.
- Existing lightweight conference OWL artifact preserved as historical baseline.
- Stable identifiers for concepts, relations, evidence, datasets, mappings, CQs and evaluations.
- Structured multi-source evidence/provenance registry.
- Governed standards, trust-framework, platform, dataset and reference-implementation mappings.
- 34 frozen Core semantic patterns and 55 frozen Core relations.
- 68 profile concepts and 65 current profile relations after DDD regression repair `CM4DI-R1020`.
- 52 governed CQs with explicit Domain and governed-relation traceability.
- DDD problem-space model: Digital Identity Management overall Domain, 15 subdomains and 13 Bounded Contexts.
- Four stable cross-domain integration Profiles: Enterprise Identity, Verifiable Credential, Technical Identity and Governed Identity.

## DDD Governance
CM4DI explicitly distinguishes:
- **Domain/Subdomain** — problem-space knowledge/capability boundary;
- **Bounded Context** — model and Ubiquitous Language ownership boundary;
- **Profile** — cross-domain standards/platform/ecosystem integration view;
- **Ontology Module** — formal OWL packaging/import unit.

These terms MUST NOT be used interchangeably. Canonical Domain and Bounded Context names MUST NOT contain `&`; slash-composed multi-area labels are retained only as historical aliases where needed.

Authoritative DDD artifacts:
- `model/journal-v2/ddd/DOMAIN_REGISTRY_v2.csv`
- `model/journal-v2/ddd/CONCEPT_DOMAIN_ASSIGNMENT_v2.csv`
- `model/journal-v2/ddd/BOUNDED_CONTEXT_REGISTRY_v2.csv`
- `model/journal-v2/ddd/CONTEXT_MAP_v2.md`
- `model/journal-v2/ddd/DOMAIN_PROFILE_MATRIX_v2.csv`
- `model/journal-v2/ddd/PROFILE_DOMAIN_CONTRACTS_v2.md`
- `model/journal-v2/ddd/WAVE7_MODULE_ARCHITECTURE_INPUT.md`

## Planned Capabilities
- DDD-derived canonical OWL module graph and version IRIs.
- OWL/SHACL formalization and synchronized serializations.
- ROBOT/HermiT logical validation.
- Executable SPARQL competency-question evaluation.
- Logical, structural, ontological, coverage, cross-paradigm, empirical and reproducibility evaluation.
- Ontology-aligned data/instance mappings and evaluation datasets without treating dataset schemas as ontology authority.
- Research publication and release traceability.

## Deviations
- OGCM-RF itself is currently an experimental development baseline; CM4DI therefore records adoption without claiming formal conformance.
- The historical conference-release files remain in their existing root locations until a controlled migration plan is executed.
- DDD is used to organize semantic ownership; this does not imply that every Bounded Context must become a microservice or an OWL module. Such alignment is made only when justified by the product/formal architecture.

## Model-Specific Extensions
CM4DI adds research-governance concerns specific to digital identity, including:
- cross-paradigm identity Profiles defined as integration views rather than Domains;
- standards and trust-framework evidence;
- enterprise/cloud IAM mappings;
- verifiable-credential and wallet mappings;
- workload, device and emerging agent-identity mappings with separate DDD subdomains;
- explicit Trust Governance and Government Identity separation;
- a segregated discovery track for Social Identity concepts that are not automatically admitted to CM4DI;
- DDD Context Map and Anticorruption Layer guidance for translating external vendor/protocol vocabularies into canonical CM4DI semantics.