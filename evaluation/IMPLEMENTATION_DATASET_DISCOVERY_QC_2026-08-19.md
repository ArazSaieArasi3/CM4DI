# CM4DI Journal V2 — Reference Implementation / Dataset Discovery QC

**Date:** 2026-08-19  
**Scope:** Issue #7 — reference implementations, GitHub repositories and datasets

## QC result

**Overall status: PASS — research-grade implementation/data evidence baseline for Gate-B and later Gate-D preparation.**

This PASS means the selected repositories/test suites and datasets are sufficiently authoritative, provenance-aware, diverse and semantically mapped for the bounded Issue #7 objective. It does **not** mean that the final evaluation experiments have already been executed; executable evaluation is intentionally deferred until the ontology scope/model are frozen.

## Quantitative summary

- Curated GitHub/reference artefacts: **12** across W3C, OpenID Certification, EUDI Wallet, SPIFFE, Keycloak and MOSIP.
- Dataset registry entries: **4**.
- Recommended primary empirical datasets: **3** — LANL authentication, Zenodo RBA, World Bank ID4D 2025.
- Optional person-level government-ID complement: **1** — Global Findex 2025 world microdata/ID4D module.
- New evidence records: **15** (`CM4DI-EVID0091`–`CM4DI-EVID0105`).
- Total evidence IDs allocated across all completed discovery streams: **105**.
- Primary evaluation portfolio combines conformance + reference implementation + empirical dataset evidence: **PASS**.
- Canonical OWL unchanged from `main`: **PASS** — identical blob SHA `e04ae62319aac1c123877b0b03acf3f5137a9849`.
- Canonical OntoUML/draw.io unchanged from `main`: **PASS** — identical blob SHA `0dce512f4c0611ccaf2fd5665d6148fb379b22af`.

## Quality assessment

| Dimension | Score | Rationale |
|---|---:|---|
| Source authority / ownership | 5.0 / 5 | Curated artefacts are owned by W3C, OpenID Certification, the official EUDI Wallet organization, SPIFFE, Keycloak and MOSIP; datasets come from LANL, Zenodo/academic authors and World Bank. |
| Maintenance/status verification | 4.9 / 5 | Core selected repositories are non-archived and showed current/recent activity at review; maintenance must still be rechecked near submission. |
| Dataset provenance / persistent identifiers | 5.0 / 5 | LANL and RBA have DOIs; Findex has a DOI; ID4D is anchored in the World Bank Data Catalog with public versioned metadata. |
| License/access discipline | 4.7 / 5 | EUDI/SPIRE/Keycloak/MOSIP and datasets have recorded licenses/access terms where verified; some W3C/OpenID repository metadata reports NOASSERTION, so code reuse is explicitly blocked pending license inspection. |
| Evidence-type diversity | 5.0 / 5 | Conformance suites, reference implementations, production IAM, workload runtime, foundational-ID implementation and empirical datasets are all represented. |
| Semantic mapping utility | 4.9 / 5 | Artefacts are mapped to CM4DI concepts/relations/CQ families and anti-conflation safeguards rather than copied as implementation taxonomies. |
| Evaluation-portfolio design | 4.9 / 5 | The portfolio is intentionally complementary: VC/DID/OpenID conformance, wallet/workload/enterprise/foundational scenarios, authentication traces, contextual login attempts and government-ID indicators. |
| Boundedness / saturation discipline | 5.0 / 5 | Additional repos/datasets are not retained when they only add count; Kaggle copies are unnecessary because primary sources exist. |
| Reproducibility readiness | 4.8 / 5 | DOI/source/license, sample-policy and mapping requirements are defined; runnable scripts/mappings will be produced after Gate C/D. |
| Gate-B contribution | 4.8 / 5 | Implementation/data evidence reinforces several cross-wave candidates and supplies evaluation feasibility evidence without prematurely modifying the ontology. |

**Execution-quality estimate: ~4.8/5 (approximately 96%) for the bounded Issue #7 objective.**

## Validated findings

### 1. Test suites and datasets play different epistemic roles
Official W3C/OpenID test suites are strongest for conformance and interoperability behavior; operational repositories are strongest for identifying real implementation boundaries; datasets are strongest for instantiation, competency questions and scale/trace evaluation. They should not be collapsed into one generic evidence category.

### 2. Account/authentication distinctions are empirically testable
The LANL and RBA datasets make `Account/User representation`, `AuthenticationAttempt/Event`, `AuthenticationResult` and contextual observations executable evaluation targets. They do not justify human/legal identity assumptions from pseudonymous user IDs.

### 3. Wallet/VC semantics have executable conformance surfaces
W3C VC/DID tests and EUDI wallet implementation allow the journal evaluation to test mappings involving issuer/holder/verifier, credential subject, credential status, identifier/controller and issuance/presentation flows without inventing toy examples.

### 4. Workload identity distinctions are executable
SPIRE provides a concrete path for testing Workload ≠ SPIFFE ID ≠ SVID ≠ Attestation ≠ TrustDomain, strongly complementing the conceptual evidence from Issue #6.

### 5. Enterprise/foundational profiles have reproducible implementations
Keycloak and MOSIP offer realistic implementation surfaces for account/profile/session/federation and registration/issuance/authentication/partner-lifecycle scenarios respectively, while their product/module labels remain profile mappings rather than Core ontology classes.

### 6. Government identity evaluation requires both system- and person-level evidence
ID4D 2025 is the preferred primary dataset for system/country digital-ID capability and coverage. Global Findex 2025 is an optional complement when person-level ownership/use questions are needed; it should not be used to infer technical assurance or operational authentication behavior.

## Residual limitations

1. Final runnable experiments have not yet been executed because candidate admission and OntoUML/OWL design must be frozen first.
2. Some official W3C/OpenID GitHub repositories do not expose a normalized SPDX license through GitHub metadata; any code/test-vector redistribution requires direct license inspection.
3. OpenID Certification's GitHub conformance repository is a read-only mirror; authoritative development is upstream on OpenID GitLab.
4. LANL contains successful authentication associations only and does not model failure, credential or authorization semantics.
5. The RBA dataset contains synthetic feature values designed to preserve selected real-world distributions/relations and must not be treated as production-security ground truth.
6. ID4D is aggregate/country-level and Global Findex is survey data; neither is an operational government-ID transaction log.
7. No public dataset in this bounded review covers every CM4DI paradigm, which is why evaluation uses triangulation rather than one synthetic completeness claim.
8. Raw multi-GB datasets should not be committed to the repository; reproducible sampling/mapping metadata should be versioned instead.

## Exit decision

Issue #7 can be closed as **completed**. The next recommended sequence is:
1. Issue #2 — Academic literature and competing ontologies;
2. Issue #8 — Social-identity side track/separation;
3. Issue #9 — cross-stream deduplication, candidate normalization and Gate-B decision package.

This order ensures the Gate-B scope lock uses normative, government, operational, non-human, implementation/data and scholarly evidence together.