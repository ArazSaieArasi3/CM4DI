# Framework Adoption

CM4DI follows **OGCM-RF — Ontology-Grounded Conceptual Model Repository Framework** for its journal-extension research and ontology evolution.

**Framework Version:** 0.1.0 development baseline  
**Conformance Status:** Adoption in progress; no formal conformance claim yet.

## Implementation Profile
See `REPOSITORY_PROFILE.yaml`.

## Implemented Capabilities
- Existing UFO-grounded and OntoUML-specified conceptual model.
- Existing lightweight OWL artifact.
- Existing field registry and conceptual diagram.
- Existing pharmaceutical ecosystem case study.
- Stable base IRI: `https://w3id.org/cm4di#`.

## Planned Capabilities
- Separation of stable CM4DI Core from ecosystem and protocol profiles.
- Stable identifiers for concepts, relations, competency questions, evidence, mappings, datasets, and evaluations.
- Structured evidence and provenance registry.
- Standards, trust-framework, platform, dataset, and reference-implementation mappings.
- OWL/SHACL formalization and synchronized serializations.
- Competency-question and SPARQL evaluation.
- Logical, structural, ontological, coverage, cross-paradigm, empirical, and reproducibility evaluation.
- Research publication and release traceability.

## Deviations
- OGCM-RF itself is currently an experimental development baseline; CM4DI therefore records adoption without claiming formal conformance.
- The historical conference-release files remain in their existing root locations until a controlled migration plan is executed.

## Model-Specific Extensions
CM4DI adds research-governance concerns specific to digital identity, including:
- cross-paradigm identity profiles;
- standards and trust-framework evidence;
- enterprise/cloud IAM mappings;
- wallet and verifiable-credential mappings;
- workload, device, and emerging agent-identity mappings;
- a segregated discovery track for social-identity concepts that are not automatically admitted to CM4DI Core.
