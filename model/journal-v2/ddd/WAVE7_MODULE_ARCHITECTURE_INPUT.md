# CM4DI Journal V2 — Wave 7 Module Architecture Input

## Status
Normative input from DDD refactor #50. This document replaces the earlier automatic assumption that each Profile should become exactly one OWL module.

## Governing equation
**Domain != Bounded Context != Profile != OWL Module**

- Domain/Subdomain organizes the problem space.
- Bounded Context owns a controlled language/model boundary.
- Profile composes multiple contexts for standards/platform/ecosystem interoperability.
- OWL Module is a formal packaging/import unit optimized for semantic cohesion, dependency direction, reuse and reasoning.

## Frozen semantic source
Wave 7 MUST preserve the Gate-C frozen Core concept/relation identities unless a separately governed semantic change is approved. The DDD refactor changes ownership/packaging inputs, not those identity criteria.

## Recommended formalization strategy

### 1. Core ontology
Maintain one stable CM4DI Core ontology as the principal semantic entrypoint for the 34 Gate-C Core concepts and 55 Gate-C Core relations. Avoid fragmenting the already frozen cross-paradigm Core merely to mirror every DDD subdomain.

### 2. Context-aligned extension modules
Create extension modules only where Wave-6/Profile concepts introduce semantics beyond Core. Candidate modules are:
- `identity-administration`
- `federation`
- `credential-exchange`
- `workload-identity`
- `device-identity`
- `agent-identity`
- `trust-governance`
- `government-identity`

Small extension constructs whose owning subdomain already largely resides in Core may be placed in carefully bounded extensions or in a compatible formal layer after dependency analysis:
- Authentication extension: Session.
- Authorization extension: PermissionBundle, AccessPolicy, AccessCondition, AccessGroup, GroupMembership.
- Credential lifecycle extension: Issuer role if keeping it outside Core.

The number of final OWL modules is therefore a Wave-7 engineering outcome, not pre-fixed to four.

## Aggregate profile entrypoints
P01–P04 MAY be exposed as aggregate ontology/import entrypoints or mapping bundles that import the relevant context-aligned modules:
- P01 Enterprise Identity Profile aggregates administration, federation, authentication and authorization extensions.
- P02 Verifiable Credential Profile aggregates credential lifecycle/exchange and relevant trust constructs.
- P03 Technical Identity Profile aggregates workload, device and agent modules plus shared authorization/credential/evidence semantics.
- P04 Governed Identity Profile aggregates trust-governance and government-identity modules plus assurance/establishment semantics.

Aggregate profile entrypoints MUST NOT own duplicated class definitions.

## Dependency constraints
1. Extension modules import/reuse Core; Core MUST NOT import extension/profile modules.
2. Cross-extension imports SHOULD follow the DDD Context Map and remain acyclic where possible.
3. Shared semantics used by two extensions are not automatically promoted to Core; promotion requires a semantic change decision.
4. Vendor/protocol terms remain mapping artifacts unless there is an independently justified profile class.
5. Technical TrustDomain/TrustBundle semantics MUST NOT import/retype institutional TrustFramework/TrustRegistry as equivalent.
6. Government Identity MAY depend on Trust Governance and Credential semantics but Trust Governance MUST NOT require Government Identity.
7. Device and Agent modules MUST NOT import Workload Identity merely because all are surfaced through P03.
8. Bounded Context names and Domain names MUST NOT contain `&`.

## Formal projection cautions
- UFO `roleMixin`, `relator`, `event`, `situation` and dependence semantics require documented OWL projections; OWL class hierarchy alone is not a substitute for the conceptual model.
- Conceptual cardinalities should be divided between OWL axioms and SHACL constraints according to open-world/closed-world semantics.
- `linkedAccount` (`CM4DI-R1020`) must not imply `owl:sameAs` or subject identity; it is evidence-governed correlation/co-reference.
- CQ relation traceability in `research/CQ_RELATION_TRACEABILITY_v2.csv` identifies constraints/properties still requiring formalization.

## Wave-7 entry criteria
- #50 DDD regression audit PASS.
- all 102 concepts assigned to a primary Domain.
- all 52 CQs and 68 mappings traceable to Domains/contexts.
- zero orphan governed CQ concept references.
- Gate-C Core semantic integrity preserved.
- conference baseline remains unchanged.

## Wave-7 deliverable rule
Before writing module OWL files, Wave 7 must first publish a machine-readable module graph with module ID, ontology IRI, version IRI, imports, owned entities, reused entities, Bounded Context alignment and aggregate Profile membership.