# CM4DI Journal V2 — GitHub Benchmark Registry

**Review date:** 2026-08-19  
**Purpose:** bounded reverse-benchmark of authoritative/mature identity implementations and test suites. This is not a popularity ranking.

## Selection dimensions

Repositories were retained when they contribute at least one of the following:
- authoritative conformance behavior tied to an identity standard;
- official reference implementation of a regulated/governed identity ecosystem;
- mature operational implementation exposing identity objects/events/lifecycle boundaries;
- reproducible workload/foundational-ID scenarios not available in standards text alone.

## Curated groups

### A. Standards conformance
- `w3c/vc-data-model-2.0-test-suite` — primary VC 2.0 conformance surface.
- `w3c/vc-test-suite-implementations` — cross-implementation participation/coverage.
- `w3c/vc-bitstring-status-list-test-suite` — credential-status lifecycle behavior.
- `w3c/did-test-suite` — DID/controller/document/verification-method conformance.
- `openid-certification/conformance-suite` — OpenID certification/conformance engine (GitHub mirror; authoritative upstream is OpenID GitLab).

### B. Government / wallet reference implementation
- `eu-digital-identity-wallet/eudi-lib-ios-wallet-kit` — official EUDI Wallet reference-implementation library; useful for issuance/presentation/holder/verifier scenario extraction.
- `eu-digital-identity-wallet/eudi-wallet-reference-implementation-roadmap` — implementation scope/status evidence, not a runtime itself.

### C. Workload identity
- `spiffe/spire` — SPIFFE Runtime Environment; strong evidence for workload attestation, SPIFFE ID/SVID issuance, trust domains and federation.
- `spiffe/spire-examples` — reproducible workload-identity scenarios.

### D. Enterprise IAM
- `keycloak/keycloak` — mature open-source IAM/SSO implementation used for reverse-benchmarking account/profile, realm, client, broker/IdP, user federation, session and access constructs.

### E. Foundational identity
- `mosip/mosip-ref-impl` — official reference/demo implementations of MOSIP modules.
- `mosip/mosip-functional-tests` — end-to-end functional-test surface for registration/issuance/authentication/partner workflows.

## Maintenance signal

At the review date, the core retained repositories were non-archived. W3C VC 2.0, OpenID conformance mirror, EUDI wallet kit, SPIRE, Keycloak and MOSIP reference implementation all showed recent activity/current maintenance signals. Maintenance is a temporal attribute and must be rechecked before final manuscript submission.

## License discipline

Where GitHub exposes a recognized SPDX license, it is recorded in `REFERENCE_IMPLEMENTATION_REGISTRY.csv`. Where GitHub returns `NOASSERTION` or the license was not independently verified, the registry explicitly says to inspect the repository/upstream license before copying code. Conceptual reverse-benchmarking and factual citation of repository behavior do not imply permission to redistribute code.

## Exclusion / saturation rule

Additional identity repositories were not retained merely because they are popular or implement OIDC/VC. Once the selected set covered conformance, wallet/government, enterprise IAM, workload identity and foundational ID, further repositories were treated as optional unless they introduced a genuinely new semantic distinction required by a Gate-B question.

## How these repositories may influence CM4DI

Allowed:
- identify recurring actor/artifact/event/state boundaries;
- build scenario mappings;
- derive competency questions;
- compare profile coverage;
- use open test vectors/examples under their applicable licenses.

Not allowed:
- promote implementation class names directly into Core;
- treat API/data-model structure as an ontology;
- equate vendor `role`, `realm`, `identity`, `credential` or `session` with CM4DI concepts without normalization;
- infer conceptual necessity from repository popularity alone.
