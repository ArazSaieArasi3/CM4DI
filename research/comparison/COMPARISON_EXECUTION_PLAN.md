# Comprehensive Comparison Execution Plan

Owner: Issue #135

## Goal
Execute a publication-grade, two-way comparison only after the source-specific deep-dives have enough evidence to support stable mapping decisions.

## Phase C0 — Schema and governance
Status: **completed in bootstrap**.
- comparison methodology defined;
- allowed mapping predicates defined;
- reverse-coverage requirement defined;
- DDD and Social Identity boundary rules preserved;
- initial CSV schemas created.

## Phase C1 — Source readiness
Inputs:
- #62 EU/EUDI;
- #63/#92–#98 standards and frameworks;
- #64/#99–#105 competitors;
- #65/#105 neighbors;
- #72/#78–#90 operational IAM/cloud products;
- #73 persistence/directories;
- #74 datasets;
- #75 implementations;
- #106–#133 discovery expansions where material.

A source family is comparison-ready when material rows have exact source/version/status, adequate coverage locators or explicit blocked status, and raw semantic constructs have at least provisional disposition.

## Phase C2 — Source-level comparison
Populate `COMPREHENSIVE_SOURCE_COMPARISON_MATRIX.csv`.
Purpose: reviewer-level overview of scope, foundations, semantic coverage, formalism, evaluation and CM4DI delta.

## Phase C3 — Fine-grained semantic mapping
Populate external→CM4DI matrices for concepts, relations, roles/events, lifecycle and constraints.
Every row must include source locator, mapping predicate, confidence, semantic difference and disposition.

## Phase C4 — Reverse coverage audit
Start from the governed CM4DI baseline rather than from external sources.
Audit all concept IDs, relation IDs, Domains, Bounded Contexts and CQs against external support/contrast evidence.
This phase detects unsupported CM4DI constructs and areas where CM4DI contributes distinctions absent from direct competitors.

## Phase C5 — Neighbor reuse/import decisions
Consume #65/#105 to freeze `reuse`, `align`, `bridge`, `specialize`, `import-module`, or `do-not-import` decisions.
No dependency is imported only for conceptual similarity; formal compatibility, license, maintenance, reasoning impact and dependency cost must be evaluated.

## Phase C6 — Standards and framework conformance view
Produce standards/EUDI/trust-framework coverage matrices by Domain/BC, concept/relation and CQ.
This is semantic alignment evidence, not a certification claim unless executable conformance evidence justifies it.

## Phase C7 — Operational realization view
Compare IAM/cloud/SSO/IGA/PAM/AuthZ/proofing/workload/agent implementations against CM4DI.
Operational objects are implementation mappings, never ontology authority.

## Phase C8 — Formal ontology comparison
Compare upper-ontology commitments, OWL/SHACL/FOL formalization, modularization, reasoning, identity criteria and equality/co-reference semantics.
This phase feeds #69.

## Phase C9 — Publication synthesis
Produce:
- integrated positioning synthesis;
- gap/delta ledger;
- direct-competitor table candidates;
- standards/framework table candidates;
- neighbor reuse table candidates;
- claim-evidence updates for #67.

## Phase C10 — Regression handoff
All semantic deltas discovered through comparison go to #66. No direct silent edits to Gate-C concepts or Wave-7 module ownership are permitted.

## Stop conditions
Do not declare the comparison complete while:
- a material direct competitor has unknown full-text/coverage status;
- material EUDI/standards sources have unrecorded coverage;
- a CM4DI governed concept/relation has no reverse-coverage status;
- a neighbor ontology has no explicit reuse/alignment disposition;
- unresolved semantic conflict could change module ownership or formal commitments.
