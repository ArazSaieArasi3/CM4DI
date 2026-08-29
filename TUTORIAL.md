# CM4DI Tutorial — Evidence to Governed Semantic Decision

This tutorial explains the repository workflow without redefining canonical ontology semantics.

## Exercise 1 — Trace an external term
Example: an EUDI Wallet `Wallet-Relying Party`.
1. Find its source in `evidence/catalogs/EU_REGULATORY_FRAMEWORK_CATALOG.csv`.
2. Find source coverage in `conceptualization/source-mining/SOURCE_COVERAGE.csv`.
3. When mined, locate the raw source-native term in `RAW_SOURCE_CONCEPTS.csv`.
4. Read its semantic disposition in `SOURCE_RECONCILIATION.csv`.
5. Follow any mapped CM4DI concept/relation to the governed registries.
6. Check Domain/Bounded Context ownership.
7. Check CQ impact and any standards/profile mapping.

A source term is never promoted to a Core class merely because it appears in law, a standard or a product.

## Exercise 2 — Trace a CM4DI concept
Example: `IdentitySubject`.
1. Locate the stable concept ID in the Gate-C Core concept registry.
2. Check its UFO/OntoUML stereotype and definition.
3. Inspect Domain assignment and neighboring Contexts.
4. Find CQs that require it.
5. Review standards/framework/competitor evidence that supports or challenges it.
6. When Wave 7 is approved, trace it into the formal module/OWL artifact and tests.

## Exercise 3 — Compare a neighboring ontology
Example: PROV-O.
1. Read `NEIGHBOR_ONTOLOGY_CATALOG.csv`.
2. Identify overlap with CM4DI Evidence/provenance semantics.
3. Use #65 reuse/align/bridge decision rather than creating duplicate generic provenance classes.
4. Confirm any final import/mapping in the formal ontology manifest.

## Exercise 4 — Validate a journal claim
Example: “CM4DI is an integrated reference ontology”.
1. Read the journal research contract and claim ceiling.
2. Check Source Completeness status.
3. Check strongest competitor comparison.
4. Check neighbor-ontology integration decisions.
5. Check formal ontology/reasoner/SHACL/CQ results.
6. Check standards and EU/EUDI coverage.
7. Check the exact evaluated release bound to PUB-003.

If one required evidence layer is missing, reduce the manuscript claim rather than extrapolating from intended work.

## Safety rule
Tutorial examples are instructional only. Canonical semantics live in governed registries/decisions and later in approved formal artifacts.
