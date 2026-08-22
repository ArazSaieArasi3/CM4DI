# Gate C DDD Alignment Amendment

**Date:** 2026-08-22  
**Parent issue:** #50  
**Gate C status:** remains approved; semantic Core freeze remains authoritative.

## Why an amendment is needed
After Wave 6, a strategic DDD review found that the repository's earlier `Domain Boundaries` document mixed four distinct organizational constructs: semantic clusters, DDD Domains, ecosystem Profiles and technology groupings. Correcting that taxonomy before Wave 7 prevents formal ontology modules from inheriting a false Profile=Domain=Module structure.

## What changed
1. `Digital Identity Management` is established as the overall DDD Domain.
2. Fifteen canonical subdomains and thirteen Bounded Contexts are governed with separate stable IDs.
3. Domain, Bounded Context, Profile and OWL Module are explicitly distinct.
4. P01–P04 remain stable integration Profile IDs but receive clearer current display labels:
   - P01 Enterprise Identity Profile
   - P02 Verifiable Credential Profile
   - P03 Technical Identity Profile
   - P04 Governed Identity Profile
5. Workload Identity, Device Identity and Agent Identity are separate subdomains; Technical Identity is a Profile/grouping view rather than one monolithic Domain.
6. Trust Governance and Government Identity are separate subdomains/contexts.
7. Canonical Domain and Bounded Context names cannot contain `&`; slash-composed multi-area labels are non-canonical legacy aliases only.
8. All 102 governed concepts, 52 CQs and 68 mappings now have explicit DDD ownership/traceability.
9. Wave-7 OWL module boundaries will be derived from Context Map/dependency analysis rather than automatically mirroring four Profiles.

## What did NOT change
- Gate-C Core concept identities: 34 unchanged.
- Gate-C Core relation identities: 55 unchanged.
- UFO/OntoUML stereotype decisions: unchanged.
- Gate-B 75 normalized decision families: unchanged.
- Evidence IDs/grades: 134 unchanged.
- Mapping IDs/predicates: 68 unchanged.
- CQ IDs: 52 unchanged.
- Social Identity exclusion: unchanged.
- no-MachineIdentity rule: unchanged.
- conference `CM4DI.owl` and published draw.io artifacts: unchanged.

## Regression repairs discovered during the amendment
The audit found two pre-existing traceability defects in Wave-5/6 research registries:

### 1. CQ0024 referenced nonexistent `IdentityLink`
No governed concept named IdentityLink existed. Creating a new class solely to satisfy the CQ would have added unjustified ontology complexity. The repair is:
- remove `IdentityLink` from required concepts;
- add `CM4DI-R1020 linkedAccount` as a profile-level Identity Administration relation between Account representations;
- explicitly forbid automatic account equality, subject equality or `owl:sameAs` inference from that link.

This increases current profile relations from the original Wave-6 count 64 to **65** and does not alter Gate-C Core.

### 2. CQ0029 used `Sponsor` rather than governed `AgentSponsor`
The CQ metadata was corrected to the stable governed concept `AgentSponsor`; no semantic entity was added.

A complete CQ→governed-relation closure artifact now records where a CQ depends on exact governed relations, derived paths, foundational role realization or Wave-7 formalization properties.

## Gate C interpretation after amendment
Gate C remains a **semantic model freeze**, not a freeze of every later documentation taxonomy. The DDD refinement preserves concept identity, stereotypes and Core/Profile semantic boundaries while improving problem-space ownership.

No Gate-C reopen is required because no Core semantic identity criterion, stereotype or cardinality was changed. The added R1020 is a supporting profile relation discovered by traceability regression and is explicitly outside the frozen Core.

## Wave-7 consequence
Formalization may proceed only after #50 regression QC is PASS. The canonical input is the frozen Core plus the DDD Context Map, not the historical assumption of one OWL module per Profile.