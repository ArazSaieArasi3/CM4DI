# CM4DI Journal V2 — Wave 6 Completion Package

**Date:** 2026-08-22  
**Status:** COMPLETE — profiles and mappings ready for formalization.

## Inputs
- Gate C approved Core freeze.
- `PROFILE_INTERFACE_CONTRACTS_v2.md`.
- 134-item evidence base and Gate-B synthesis.
- OGCM-RF concept/CQ/mapping governance rules.

## Outputs
- Gate C approval record.
- Governed profile concept registry: 68 profile concepts.
- Governed profile relation registry: 64 profile relations.
- Four human-readable profile designs: P01 Enterprise/Federation; P02 Wallet/VC; P03 Machine/Workload/Device/Agent; P04 Trust/Assurance/Government.
- Governed mapping registry: 68 mapping assertions using exact/narrower/related/implementation semantics.
- Profile CQ registry: 20 new CQs, bringing total governed CQs to 52.
- Cross-profile integration matrix with six combined scenario checks.
- Wave-6 QC report: PASS (~4.9/5, ~98%).

## Architecture retained
`Core + P01 + P02 + P03 + P04`, with all profiles importing/reusing the frozen Core. Cross-profile reuse is explicit and cannot silently change Core meaning.

## Important profile decisions
1. P01 owns Account/Profile, enterprise Federation, Provisioning, Session and IAM-specific permission-bundle/policy constructs.
2. P02 owns Issuer/Holder/PresentationVerifier, Wallet/HolderService, CredentialPresentation, DID control/verification-method and selective-disclosure constructs.
3. P03 owns Workload/Device/SoftwareAgent rigid kinds plus service-account/principal/managed-identity, attestation, SPIFFE and agent-identity patterns. No `MachineIdentity` superclass.
4. P04 owns trust/governance frameworks, registries/lists/anchors/chains, conformity/governance roles and lifecycles, legal identity/PID/government attestation and framework assurance mappings.

## Cross-profile bridges
- P01↔P03: workload federation and enterprise machine identities.
- P02↔P04: EUDI wallet, PID and governed attestations.
- P01↔P04: governed enterprise federation/provider participation.
- P01↔P03: AI-agent enterprise access.
- P03↔P04: technical trust domains related to but not subsumed by governance/trust frameworks.

## Mapping discipline
Exact equivalence is rare and used only where stable semantics warrant it. Vendor/product constructs are normally `implementation` mappings. Lexical similarity alone never justifies ontology equivalence.

## Change control
Published conference baselines remain unchanged:
- `CM4DI.owl`: main = journal-v2 SHA `e04ae62319aac1c123877b0b03acf3f5137a9849`.
- `CM4DI-Generation2-Version15.drawio`: main = journal-v2 SHA `0dce512f4c0611ccaf2fd5665d6148fb379b22af`.

## Next wave
Wave 7 — Formal Ontology & Automation:
1. define canonical ontology module graph and version IRIs;
2. create formal Core OWL and four profile OWL modules;
3. translate only appropriate conceptual constraints into OWL DL;
4. create SHACL shapes for structural/closed-world constraints;
5. generate deterministic TTL/RDF/XML/JSON-LD/TriG/N-Quads serializations as appropriate;
6. implement ROBOT/HermiT validation;
7. formalize mappings without excessive `owl:equivalentClass` use;
8. implement SPARQL CQ suite from 52 governed CQs;
9. add CI regression workflow;
10. prepare Gate D evaluation-design lock package.

Wave 7 may now proceed without another scope decision because Gate C has already frozen conceptual semantics.