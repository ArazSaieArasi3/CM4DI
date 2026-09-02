# CM4DI Reuse, Extend, Align, Bridge or Create Decisions

Current review update: 2026-09-02  
Owners: #65, #105  
Status: **Provisional — formal import decisions remain blocked on #60/#66/#69.**

## Decision principle
CM4DI is intended to be an integrated reference ontology for digital identity. Integration does not mean absorbing every adjacent semantic domain. Mature neighboring ontologies should remain semantic owners where their scope is generic and orthogonal to digital identity.

| Neighbor | Provisional decision | CM4DI role | Rationale |
|---|---|---|---|
| gUFO | Reuse + align; selective import candidate | foundational semantics | CM4DI is UFO-grounded; gUFO provides a lightweight OWL 2 DL implementation of UFO suitable for specialization/instantiation. Exact import scope is a #69 formal decision. |
| ONTrust | Align + bridge | generic trust semantics | Avoid rebuilding a generic ontology of trust. CM4DI retains identity-specific TrustFramework, TrustRegistry, TrustAnchor and TrustReference semantics while aligning generic trust relation/assessment patterns. |
| PROV-O | Align + bridge | provenance | Use generic attribution, derivation, generation/use and provenance relations instead of inventing a CM4DI-wide provenance ontology. |
| W3C ORG | Bridge + reuse | organization and membership | B2B/governance organization structure and membership are neighboring semantics. Organization must not be collapsed into AccessGroup and Membership must not be collapsed into AccessGrant. |
| ODRL | Bridge | rich authorization-policy expressions | CM4DI retains a minimal identity-authorization kernel; ODRL can express richer permissions, prohibitions, duties and constraints where needed. |
| DPV | Bridge | privacy/data processing/legal basis | Privacy, purpose, processing, consent and legal-basis semantics remain outside Core and should use DPV mappings when required. |
| W3C VC/RDF vocabularies | Align/bridge in credential profile | credential ecosystem | Exact RDF vocabulary reuse is appropriate where stable terms match profile semantics; do not make protocol vocabulary the conceptual Core. |
| SKOS / Dublin Core | Metadata-only reuse when justified | labels/metadata | Not domain ontology dependencies; use only for metadata/terminology requirements. |

## Key anti-conflation decisions
1. `TrustAssessment != TrustFramework != TrustRegistry != TrustAnchor`.
2. `Organization != AccessGroup`.
3. organizational `Membership != GroupMembership` used for access grouping and `!= AccessGrant`.
4. provenance attribution/derivation does not imply trust, truth, identity binding or semantic equality.
5. ODRL Permission is not automatically exact-equivalent to the CM4DI minimal Permission concept.
6. DPV Purpose/LegalBasis do not become CM4DI Core concepts merely because EUDI or product flows express intended use/consent.
7. gUFO foundational types guide formal projection; vendor classes named Role/Identity/Principal are not equivalent by label.

## Formalization implications
- #69 must decide whether gUFO is imported directly, selectively reused, or aligned by local projection patterns.
- ONTrust import versus bridge must be tested for gUFO version compatibility, module dependencies and reasoning cost.
- PROV-O/ORG/ODRL/DPV should default to bridge/alignment rather than mandatory Core imports unless executable use cases justify imports.
- SHACL may be required for integrity constraints that are not safely captured through OWL open-world axioms.

## Remaining before freeze
- exact class/property/axiom extraction for each material neighbor;
- license/version/maintenance and import-graph review;
- W3C VC vocabulary alignment details;
- additional access-control/security ontology discovery;
- cross-check against #135 comprehensive mapping matrices;
- #66 semantic regression and #69 formal commitment approval.
