# CM4DI Deep-Dive Discovery Protocol

Status: active for journal-v2 Source Completeness.

## Purpose
This protocol governs fine-grained discovery of standards, regulatory frameworks, products, services, ontologies, papers, datasets, repositories, directories and implementation artifacts. The goal is not merely to collect terms. Each deep-dive must discover and reconcile **entities/concepts, roles, relations, events, lifecycle states, constraints, rules, data objects, API boundaries, DDD signals, competency-question implications and research/product opportunities**.

## Unit of analysis
A material source family may have an Epic, but every materially distinct product, ontology, standard suite or framework receives an individually auditable Issue when its semantics cannot be safely collapsed into another item.

## Pass A — source inventory
Record authoritative URLs/DOIs/repositories, issuer/owner, exact version/date/status, supersession, license/access, source sections/endpoints/repos, and inaccessible/blocked material.

## Pass B — raw extraction
Extract without premature normalization:
- entity/object/type terms;
- contextual roles;
- relation/association terms and their direction/cardinality;
- events/processes;
- lifecycle states and transitions;
- constraints/invariants/preconditions/postconditions;
- trust/assurance/governance constructs;
- policy/authorization constructs;
- identifiers, claims, credentials, evidence and proof artifacts;
- directories/accounts/profiles/sessions;
- APIs/messages/data-schema objects only when semantically material;
- implementation patterns and storage boundaries;
- explicit definitions and source locators.

## Pass C — semantic normalization
For every raw item classify the disposition as one of:
`existing-concept`, `existing-relation`, `existing-event`, `existing-constraint`, `mapping-only`, `profile-refinement`, `DDD-boundary-signal`, `formalization-signal`, `CQ-delta`, `evaluation-signal`, `neighbor-reuse`, `candidate-new-concept`, `candidate-new-relation`, `candidate-new-event`, `candidate-new-constraint`, `future-research`, or `reject-with-rationale`.

Lexical similarity is never sufficient for equivalence. Vendor/protocol terms do not define CM4DI semantics by themselves.

## Pass D — relation and lifecycle analysis
Every deep-dive must explicitly ask:
1. What objects are related?
2. Is the relationship material, derived, temporal, contextual, normative or representational?
3. Is the relationship many-to-many, scoped, versioned or time-bounded?
4. Does the source model an event that creates, changes, suspends, revokes, expires, links or delegates a relationship?
5. Does the relation need a relator/event/state artifact rather than a simple OWL object property?
6. Does the source distinguish identity equality, co-reference, account linking, representation and subject identity?

## Pass E — DDD impact
Map findings to the governed Domain and Bounded Context registries. Revalidate cohesion, language and ownership. A product, protocol, database or OWL module never defines a Domain. Canonical Domain and Bounded Context names must not contain `and`, `&`, or slash-composed semantic centers.

## Pass F — formal ontology impact
Record implications for UFO/OntoUML stereotype, identity principle, rigidity, dependence, mediation, participation, event/situation/mode, disjointness, cardinality, property characteristics and OWL-versus-SHACL allocation. Formal changes are deferred to #69 after Source Completeness.

## Pass G — product/data/architecture impact
Record capabilities, service candidates, API/event adapters, persistence implications, ontology-relational mappings, quality scenarios and potential product opportunities without promoting implementation artifacts to ontology authority.

## Pass H — evidence and evaluation impact
Identify affected CQs, new CQs, test data, conformance tests, benchmark scenarios and dataset needs. Every evaluation result later binds to ontology/release SHA.

## Pass I — open discovery
Every deep-dive must end with a radar pass asking what was not in the original plan: new products, ontologies, standards, datasets, repositories, research gaps, reusable patterns or product opportunities. Record these in the Discovery Radar and Opportunity Ledger.

## Completion rule
A deep-dive is complete only when its material sources have explicit coverage, every extracted material item has a disposition, relation/lifecycle/constraint analysis is recorded, CM4DI mappings are traceable, DDD/formal/CQ impacts are stated, and all new discoveries are triaged.
