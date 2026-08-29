# CM4DI PUB-003 Journal Research Contract

**Research:** R-015 CM4DI  
**Publication:** PUB-003  
**Precursor:** PUB-002 — *An Ontology-Driven Conceptual Model for Digital Identity with Trust Integration*  
**Status:** active contract baseline; Source Completeness and formal evaluation still pending.

## Scientific objective
Engineer and evaluate a **UFO-grounded, cross-paradigm digital-identity reference ontology** that provides one coherent semantic integration layer across identity-management standards, European and global trust frameworks, enterprise/federated IAM, verifiable credentials, workload/device/agent identity and government digital identity, while explicitly aligning to mature neighboring ontologies instead of duplicating their full semantics.

## Intended contribution package
1. **Unified conceptual semantics:** a stable Core spanning subjecthood, representation, identity information/evidence, establishment, credential semantics, authentication, authorization and minimal trust/assurance hooks.
2. **DDD-governed semantic ownership:** 15 problem-space subdomains and 13 Bounded Contexts, distinct from four cross-domain ecosystem Profiles and from formal OWL module packaging.
3. **Well-founded formal ontology:** explicit UFO/OntoUML commitments and documented OWL 2 DL/gUFO projection, with SHACL used for constraints that do not belong in open-world logical axioms.
4. **Cross-standard integration:** traceable mappings to current ISO/IEC, NIST, W3C, OpenID, IETF, OASIS and FIDO sources.
5. **European regulatory and architecture integration:** explicit source/version lineage and semantic crosswalk for eIDAS/EUDI law, implementing regulations, ARF, wallet ecosystem actors, PID/EAA, relying-party registration, trust lists/anchors and conformance.
6. **Cross-ecosystem integration:** Enterprise Identity, Verifiable Credential, Technical Identity and Governed Identity Profiles as non-owning integration views over the governed semantic model.
7. **Neighbor-ontology interoperability:** explicit reuse/align/bridge decisions for UFO/gUFO, ONTrust, PROV-O, ORG, ODRL, DPV and additional qualified adjacent ontologies.
8. **Executable evaluation:** OWL profile/reasoning, SHACL, SPARQL CQs, standards/framework coverage, operational mappings, cross-paradigm scenarios, empirical/dataset instantiation and reproducibility evidence.
9. **Comparative evaluation:** strongest direct ontology and conceptual-model competitors, including current UFO-grounded and historical OWL identity ontologies.
10. **Reproducible scholarly release:** stable IDs, provenance, module/import manifest, mappings, tests, checksums and version-bound publication evidence.

## Primary research questions
- **RQ1:** What ontological distinctions are required to represent digital identity consistently across human and non-human, centralized, federated, credential-based, government and emerging agent ecosystems?
- **RQ2:** How can heterogeneous standards, regulatory/trust frameworks, operational IAM systems and neighboring ontologies be semantically integrated without embedding protocol-, vendor- or jurisdiction-specific constructs in the Core?
- **RQ3:** To what extent does the resulting CM4DI reference ontology cover and connect representative standards/frameworks while remaining logically coherent, ontologically well-founded and modular?
- **RQ4:** Can the ontology support executable competency questions, cross-ecosystem mappings and representative data/scenarios with reproducible evaluation evidence?

## Claim ceiling
The following expressions are **evaluation-dependent claims**, not assumptions:
- complete ontology;
- comprehensive ontology;
- unified/integrated ontology;
- interoperable ontology;
- validated ontology;
- reference ontology.

At manuscript time, use the strongest wording justified by Source Completeness, competitor comparison, formal evaluation, standards/framework coverage and reproducibility. Avoid `first digital identity ontology` and `first UFO-grounded identity ontology`.

## Closest-work hypothesis to test
- **MFSSIA 2026** is currently the closest direct UFO-grounded ontology competitor, but its scope is SSI challenge-response authentication in M2X rather than cross-paradigm digital identity.
- **Layouni and Pollet 2009** is an important historical OWL federated-identity ontology comparator and must be restored to the direct-competitor baseline.
- **Comb and Martin 2026** is the broadest current ontological synthesis/precursor but does not itself provide the formal cross-paradigm ontology artifact targeted by CM4DI.
- Enterprise IAM, SSI/wallet, trust/government and interoperability conceptual models are adjacent comparators rather than substitutes for the full intended contribution.

## Publication-quality gates
1. Source Completeness Gate (#60/#66).
2. Closest-work and neighbor-ontology positioning (#64/#65).
3. PUB-002→PUB-003 scientific extension delta (#67).
4. Module architecture freeze (#58/#59).
5. Formal ontology commitments and OWL/SHACL allocation (#69).
6. Executable semantic CI and validation (#70 plus Wave-7 implementation issues).
7. Gate D evaluation design lock.
8. Wave 8 multi-layer evaluation.
9. MQAP-EXT manuscript/repository synchronization and Gate E.

## Venue
MDPI *Information* remains a working direction and *Future Internet* a fallback from the prior plan; venue fit/quartile/scope must be rechecked close to submission and is not frozen by this contract.
