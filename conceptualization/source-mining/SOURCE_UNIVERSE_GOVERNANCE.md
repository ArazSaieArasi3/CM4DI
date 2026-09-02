# CM4DI Source Universe Governance

Owner: Issues #60/#61. Comparison consumer: #135.

## Current state
The source universe is intentionally represented by multiple typed registers during active Exhaustive Source Mining:
- `SOURCE_REGISTER.csv` — normative, EU/regulatory, scholarly competitor and neighbor-ontology baseline;
- `SOURCE_REGISTER_INDUSTRIAL.csv` — operational IAM/cloud/directory/implementation/dataset supplement;
- source-family deep-dive coverage files under `evidence/`;
- Discovery Radar #91 for newly discovered candidates.

These are **not competing sources of truth**. They are typed intake surfaces that converge through #61 and #66.

## Authoritative source record requirements
Every material source must ultimately have:
1. stable source record ID;
2. optional stable evidence ID when admitted to the evidence registry;
3. source family and role;
4. exact title/owner/version/date/status;
5. canonical URL, DOI or identifier;
6. authority class;
7. materiality (`material`, `supporting`, `monitor`, `excluded-with-rationale`);
8. affected CM4DI Domain/Bounded Context;
9. coverage status and source locators;
10. access limitation when applicable;
11. semantic disposition status;
12. last verified date.

## Coverage states
- `queued`
- `seeded-needs-exhaustive`
- `existing-summary_needs-exhaustive`
- `pass-1`
- `pass-2-semantic`
- `blocked-partial`
- `complete`
- `not-concept-bearing`
- `excluded-with-rationale`

A broad source list is not Source Completeness.

## Reconciliation rule
Raw constructs may be extracted freely, but ontology changes only occur through #66 after classification as:
- already covered;
- mapping only;
- profile/context refinement;
- Core candidate;
- relation/lifecycle/constraint delta;
- CQ/test delta;
- formalization delta;
- future research;
- reject with rationale.

## Comparison handoff
Issue #135 consumes source rows only when their coverage is adequate for the comparison claim being made. A blocked/partial source can appear in the comparison matrix only with explicit limitation and cannot support strong equivalence or completeness claims.

## DDD invariant
Source-local taxonomies never define CM4DI Domain names. Current DDD architecture remains 15 Domains and 13 Bounded Contexts unless #66 accepts evidence-driven change. Canonical Domain/BC names contain no `and`, `&`, or slash-composed semantic center.

## Social Identity boundary
Social Identity remains external in SemSocialIdentity. Relevant sources may create bridge mappings, but do not enter CM4DI Core merely because a product exposes social login, organization membership, profile or reputation constructs.
