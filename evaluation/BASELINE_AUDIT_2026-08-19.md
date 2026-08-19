# CM4DI Journal V2 — Baseline Repository Audit

**Audit date:** 2026-08-19  
**Branch:** `journal-v2`  
**Purpose:** establish the starting condition of CM4DI before evidence-driven journal expansion.

## Executive Assessment
The repository is a strong conference/publication baseline but is not yet a full OGCM-RF-style research knowledge infrastructure. The existing assets should be preserved and progressively organized rather than replaced. Major journal-value gaps are evidence provenance, explicit Core/Profile separation, stable research-artifact identifiers, competency questions, machine-readable mappings, deterministic formalization, layered evaluation, and scholarly release traceability.

## Existing Assets
| Area | Status | Evidence / Observation | Journal-v2 Action |
|---|---|---|---|
| Conceptual model | Present | OntoUML-oriented Draw.io model and exported image exist. | Preserve baseline; revise only after Gate B evidence synthesis. |
| Formal ontology | Present | `CM4DI.owl` exists and uses the public `https://w3id.org/cm4di#` namespace. | Perform formal inventory and conceptual-to-OWL traceability audit before refactoring. |
| Field registry | Present | `CM4DI-field-registry-v0.1.md` defines Core/Profile/Deferred fields. | Reuse as a seed for profile architecture and evidence-linked field decisions. |
| README documentation | Present | README documents core concepts, relations, trust strategy, scope and future directions. | Rebuild later as an OGCM-RF navigation entrypoint without losing the conference baseline narrative. |
| Conceptual diagram | Present | `CM4DI-Generation2-Version15.drawio` and `.jpg` exist. | Preserve as conference baseline and later add versioned journal views. |
| Domain case study | Present | Pharmaceutical ecosystem identity case study exists. | Preserve as one scenario; do not let pharma dominate journal scope. Add heterogeneous scenarios later. |
| License | Present | Apache License 2.0 file exists. | Retain unless a later artifact-specific license review requires additions. |

## Structural and Traceability Gaps
| Gap | Severity | Why It Matters | Required Action |
|---|---|---|---|
| No explicit journal-development branch before this work | Resolved | Conference and journal evolution should not be conflated. | `journal-v2` branch created; future journal work remains isolated until reviewed. |
| No OGCM-RF implementation profile | Resolved for Gate A | Repository governance was implicit. | `FRAMEWORK.md` and `REPOSITORY_PROFILE.yaml` added on `journal-v2`. |
| No research charter / gate record | Resolved for Gate A | Scope expansion can otherwise drift. | `research/RESEARCH_CHARTER.md` added. |
| No journal-v2 execution roadmap | Resolved for Gate A | Discovery, modeling, formalization and publication need explicit ordering. | `roadmap/JOURNAL_V2_ROADMAP.md` added. |
| No structured evidence registry | Critical | Journal claims and ontology changes need provenance across academic, normative and operational evidence. | Create evidence schema and registry before broad discovery. |
| No standards/framework inventory | Critical | Cross-paradigm contribution cannot be demonstrated without explicit coverage. | Build normative evidence inventory and mapping candidates. |
| No competitor ontology/model matrix | High | Novelty against recent identity/SSI ontologies must be explicit. | Build comparison matrix early in discovery. |
| No cloud/IAM platform mapping registry | High | Cross-paradigm operational relevance is not yet demonstrated. | Benchmark AWS, Entra, Google and selected IAM systems. |
| No dataset registry | High | Empirical/scenario evaluation lacks reusable provenance. | Build dataset inventory with DOI/license/access metadata where available. |
| No competency-question registry | Critical | Ontology requirements and executable evaluation are not explicit. | Define CQs after first discovery synthesis and before model freeze. |
| No machine-readable mapping artifacts | Critical | Interoperability claims are currently narrative. | Create standard/platform/profile mapping registries. |
| No SHACL constraints | High | Structural validation is absent. | Add after conceptual model freeze. |
| No SPARQL CQ suite | High | Semantic capability is not executable. | Add with CQ evaluation layer. |
| No CI/reasoner pipeline | High | Reproducibility and regression detection are limited. | Add deterministic validation after canonical ontology-source policy is fixed. |
| No release manifest / scholarly release traceability | High | Journal artifact should be citable and reproducible. | Add release manifest, versioning and archive/DOI plan before submission. |
| No conference-to-journal delta matrix | High | Journal extension must show substantial new contribution. | Build and maintain extension-delta matrix throughout manuscript development. |

## Documentation Consistency Findings
1. The README currently links the pharmaceutical case study using a `docs/` path, while the actual file is located at repository root. This should be corrected during controlled repository reorganization.
2. The README repository-content section refers to `cm4di.owl`, while the actual current filename is `CM4DI.owl`; case-sensitive paths should be normalized in the journal structure.
3. The README lists several intended documentation artifacts such as concept, relation and competency-question pages that are not yet implemented. Journal v2 should turn these intentions into governed artifacts rather than leaving them as placeholders.
4. The OWL artifact contains operational/helper vocabulary used by properties and mappings in addition to the high-level conceptual concepts listed in the README. This is not treated as an error at baseline, but it requires an explicit conceptual-model-to-formal-ontology traceability audit before the journal ontology is refactored.
5. The pharmaceutical case study is useful as a controlled validation scenario, but a journal claim of cross-paradigm applicability requires additional non-pharmaceutical and non-human identity scenarios.

## Scope Risks to Control
- **SSI gravitational pull:** avoid allowing VC/DID material to redefine the ontology as SSI-specific.
- **Vendor contamination:** do not promote AWS/Entra/Google product terms directly into Core without cross-ecosystem justification.
- **Security-scope explosion:** access control, cryptography and cybersecurity concepts enter only to the extent required for identity semantics.
- **Government-framework overload:** use national/EU frameworks as evidence and profiles, not as competing cores.
- **Social-identity conflation:** keep sociological/social-identity concepts in a segregated opportunity register unless they are required for digital-identity semantics.
- **OWL-first rework:** do not expand the formal ontology materially before evidence synthesis and conceptual-model decisions.

## Baseline Readiness
- Conference artifact preservation: **PASS**
- Journal mission and broad scope: **PASS**
- OGCM-RF adoption scaffold: **PASS**
- Evidence infrastructure: **NOT YET**
- Cross-paradigm discovery: **NOT YET**
- Revised conceptual model: **NOT YET**
- Formal journal-grade ontology: **NOT YET**
- Multi-layer evaluation: **NOT YET**
- Journal manuscript package: **NOT YET**

## Immediate Next Action
Create the structured evidence/provenance protocol and begin Wave 1–4 discovery. The first major decision after discovery is Gate B: Core/Profile/Deferred/Reject/Social-Identity scope lock.
