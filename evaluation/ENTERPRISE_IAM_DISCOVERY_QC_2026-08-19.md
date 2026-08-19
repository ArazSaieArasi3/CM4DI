# CM4DI Journal V2 — Enterprise / Cloud IAM Discovery Quality-Control Report

**Date:** 2026-08-19  
**Scope:** Issue #5 — Enterprise, cloud IAM and SSO platform discovery

## QC result

**Overall status: PASS — research-grade operational IAM evidence baseline for Gate-B preparation.**

This PASS means the bounded Issue #5 outputs are sufficiently current, authoritative, cross-platform, traceable and semantically normalized to test the standards/government abstractions against real IAM implementations. It does **not** mean that every IAM/IGA/PAM vendor or deployment pattern has been exhaustively reviewed.

## Quantitative execution summary

- Required cloud references covered: **3/3** — AWS, Microsoft Entra, Google Cloud.
- Required representative IAM platforms covered: **7/7** — Okta, Auth0, PingOne, Keycloak, ZITADEL, Ory, authentik.
- Curated operational evidence records: **25** (`CM4DI-EVID0046`–`CM4DI-EVID0070`).
- Vendor-to-neutral semantic candidates: **40** (`CAND-IAM-001`–`CAND-IAM-040`).
- High-priority anti-conflation families explicitly documented: **14+**.
- Enterprise/Federated profile decision-support artifact produced: **PASS**.
- Evidence-ID continuity/collision prevention: **PASS** via `evidence/EVIDENCE_STREAM_MANIFEST.md`.
- Canonical `CM4DI.owl` unchanged from `main`: **PASS** — identical Git blob SHA `e04ae62319aac1c123877b0b03acf3f5137a9849`.
- Canonical OntoUML/draw.io baseline unchanged from `main`: **PASS** — identical Git blob SHA `0dce512f4c0611ccaf2fd5665d6148fb379b22af`.

## Quality assessment by dimension

| Dimension | Assessment | Rationale |
|---|---:|---|
| Source authority / provenance | 5.0 / 5 | Retained evidence uses official AWS, Microsoft, Google, Okta/Auth0, Ping, Keycloak, ZITADEL, Ory and authentik technical documentation/repositories. |
| Recency / terminology verification | 4.9 / 5 | Current 2026 documentation was used where available; cloud/vendor documentation remains living material and must be rechecked near submission. |
| Required Issue #5 scope coverage | 5.0 / 5 | All three required clouds and all seven named representative IAM platforms were covered. |
| Traceability / reproducibility | 4.8 / 5 | Stable evidence IDs, source URLs, comparison matrix, candidate registry, stream manifest and decision-support artifact are committed. Cross-stream central merge remains intentionally deferred to Issue #9. |
| Semantic extraction / ontology utility | 4.9 / 5 | The review identifies account/profile, principal, session, source, broker, provisioning, grant, permission, policy, tenant/realm and mapping distinctions rather than copying product taxonomies. |
| Vendor-neutral normalization | 5.0 / 5 | AWS PermissionSet, Entra role assignment, Google role binding, Okta assignment and similar constructs are mapped to neutral patterns instead of promoted as vendor-named Core classes. |
| Semantic anti-conflation | 5.0 / 5 | IAM Role ≠ UFO Role; Account/Profile ≠ IdentitySubject; Principal ≠ Person; IdentitySource ≠ IdP; Provisioning ≠ Enrollment; Assignment ≠ Authorization; Session ≠ AuthenticationResult; Tenant/Realm ≠ IdentityContext are explicitly documented. |
| Saturation discipline | 4.8 / 5 | Hyperscale cloud, CIAM, commercial IAM and mature open-source IAM are represented. Additional vendors are unlikely to materially change the current candidate set before academic/non-human synthesis. |
| Cross-wave convergence | 4.9 / 5 | Standards candidates for authorization/federation and government candidates for provenance/lifecycle are strongly operationally confirmed. |
| Contribution to Gate-B readiness | 4.6 / 5 | Operational IAM is ready, but academic competitors, dedicated machine/device/agent identity, implementations/datasets and social-identity tracks remain open. |

**Execution-quality estimate:** approximately **4.8/5 (~96%)** for the bounded Issue #5 objective. This is a quality estimate for this discovery wave, not a completeness percentage for the ontology or journal article.

## Major validated findings

### 1. Account representation is a major missing semantic layer
Across Cognito, Entra, Okta/Auth0, PingOne, Keycloak, ZITADEL and Google Identity Platform, systems maintain platform-local user/account/profile representations that are distinct from the real identity subject. Gate B must determine how `Account` relates to `DigitalIdentity`, `IdentitySubject`, identifiers and credentials.

### 2. Principal is broader than human subject
Google, Entra, AWS and Ory authorization patterns operate on principals that may represent people, groups, workloads or federated identities. `Principal` is therefore a high-value authorization abstraction but requires UFO analysis as a role/representation, not a new synonym for IdentitySubject.

### 3. Authentication, session and durable access grants are distinct
Authentication produces a result; platforms then maintain sessions or temporary security contexts. Separately, durable assignments/grants connect accounts/principals/groups to permissions or permission bundles. These three phenomena must not collapse into one `Authorization` or `AuthenticationResult` object.

### 4. Identity source and identity provider are different functions
AWS, PingOne, Okta, Keycloak and authentik show that a source authoritative for identity/profile data may differ from the IdP that authenticates. This is especially visible when SAML/OIDC handles authentication while SCIM/LDAP/provisioning handles account materialization and synchronization.

### 5. Provisioning is not Enrollment
SCIM/JIT/directory provisioning creates and synchronizes account representations across systems. CM4DI `Enrollment` currently grounds subscriber/provider participation and should not be expanded to absorb provisioning semantics.

### 6. Vendor IAM roles must not be mapped to UFO Role
AWS roles, Google roles, permission sets, Entra roles and Keycloak roles encode permission bundles, security contexts or grant administration. They are semantically different from anti-rigid social roles used in foundational ontology modeling.

### 7. Attribute provenance/mapping gains operational confirmation
Identity values routinely cross boundaries through claims, SCIM, profile sourcing and mapping rules. This strongly reinforces government-wave Attribute Provenance/Binding candidates and justifies explicit traceable `AttributeMapping` semantics.

### 8. Tenant/realm/population is not IdentityContext
Administrative partitions define isolation/management scope. CM4DI `IdentityContext` scopes a digital identity semantically. The two may be related but must not be lexically merged.

### 9. Non-human identity is operationally unavoidable but not resolved here
Entra workload/service principals, Google service accounts/workload federation and ZITADEL service accounts confirm the need for non-human coverage. Their ontological classification is intentionally deferred to Issue #6.

## Residual limitations

1. Vendor documentation is living and product terminology can change; current status should be rechecked near manuscript submission.
2. This is a conceptual operational benchmark, not a hands-on performance/security evaluation of deployed products.
3. Full IGA/PAM ecosystems such as SailPoint and CyberArk were not added because the current issue is centered on IAM/SSO/federation and semantic saturation was reached; they can be added later only if a Gate-B gap requires governance/privileged-identity evidence.
4. Ory evidence uses official open-source repositories/product material in addition to indexed documentation because its current documentation surface is distributed across project components.
5. Detailed workload/device/agent ontology design is deferred to Issue #6 by design.
6. CIAM privacy/consent and full access-control policy languages remain outside Core scope.
7. Enterprise evidence remains a separate stream registry until Issue #9 cross-stream deduplication and normalization.

## Exit decision

Issue #5 can be closed as **completed**. The next recommended execution step is **Issue #6 — Machine, workload, device and AI-agent identity discovery** because enterprise evidence has established that the current human-centric assumptions are insufficient, but dedicated ontological analysis is required before deciding whether non-human entities belong in Core, profile modules, or mappings.