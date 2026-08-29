# Open-Source IAM and Identity Implementation Benchmark

Status: **seeded benchmark; exhaustive repository/document mining pending Issue #75**.

## Purpose
Use mature open-source implementations to test whether CM4DI's conceptual boundaries survive real software object models, state transitions and protocol integrations. Repository structures are operational evidence, not ontology authority.

| Repository | Operational focus | High-value constructs | CM4DI challenge/value |
|---|---|---|---|
| `keycloak/keycloak` | IAM, SSO, federation, user federation | Realm, User, Group, Client, Role, Session, IdentityProvider | Tests AdministrativeDomain, Account, ApplicationRegistration, Session, Federation, Provisioning and authorization mappings without copying Keycloak vocabulary into Core. |
| `zitadel/zitadel` | Multitenant IAM/CIAM/SSO | Organization, User, ServiceAccount, Project, Application, RoleAssignment, external IdP | Tests durable AccessGrant, service-account/non-human identity, operational boundary and federated account linking. |
| `ory/kratos` | Identity lifecycle | Identity, schema/traits, login, registration, recovery, verification, session | Strong case for separating Identity Administration/Authentication lifecycle from OAuth2 authorization-server concerns. |
| `ory/hydra` | OAuth2/OIDC authorization server | Client, consent/login integration, authorization/token flows | Focuses Federation/Authorization protocol boundary and shows that identity store/lifecycle need not live in the same component. |
| `goauthentik/authentik` | IAM/SSO with configurable flows | User, Group, Source, Provider, Application, Flow, Stage, Policy | Tests Anticorruption Layer discipline because platform vocabulary is highly workflow/configuration oriented. |
| `dexidp/dex` | Focused OIDC federation broker | Connector, Client, external IdP, claims | Minimal implementation useful for isolating IdentityBroker/FederationConnection from full Identity Administration. |
| `spiffe/spire` | Workload identity | Workload, SPIFFE ID, SVID, NodeAttestation, WorkloadAttestation, TrustDomain, Bundle | Strong executable support for `Workload != Identifier != Credential != Attestation != TrustDomain`. |
| `mosip/mosip-ref-impl` | Foundational/government identity | registration, proofing, issuance, authentication, partners/providers | Tests Government Identity plus Identity Establishment, Credential Lifecycle and Trust Governance integration. |
| `w3c/vc-data-model-2.0-test-suite` | VC data-model conformance | credential structures, roles, status/conformance assertions | Protocol/data-model conformance evidence for Credential Lifecycle/Exchange; not a formal-ontology validation suite. |
| `openid-certification/conformance-suite` | OpenID/OAuth/OID4VC conformance | clients, servers, flows, assertions, issuance/presentation profiles | Executable standards-profile evidence; authoritative development/mirror lineage and exact licenses must be documented. |
| `eu-digital-identity-wallet/eudi-lib-ios-wallet-kit` | EUDI Wallet reference library | wallet, credential issuance/presentation, holder/verifier interaction | Operational EU profile evidence and scenario source; legal semantics remain governed by EU law/ARF sources. |

## Repository metadata verified in the seed pass
Public/non-archived repository metadata was checked on 2026-08-29 for Keycloak, ZITADEL, Ory Kratos, Ory Hydra, authentik, Dex, SPIRE, MOSIP reference implementation, OpenID conformance suite, W3C VC 2.0 test suite and EUDI wallet kit.

## Semantic conclusions

### Mature IAM implementations reinforce DDD separation
Kratos/Hydra and Dex provide especially useful counterexamples to monolithic thinking: identity lifecycle, authentication/federation and authorization-server concerns can be operationally separated. This supports CM4DI's distinct Identity Administration, Authentication, Federation and Authorization contexts.

### Code object names are not ontology categories
`Realm`, `Connector`, `Source`, `Provider`, `Flow`, `Stage`, `Project` and database schemas are implementation constructs. They are mapped through the Anticorruption Layer and do not justify Core classes by themselves.

### Workload identity is structurally different from user-account IAM
SPIRE provides executable evidence for workload attestation and short-lived credentials that cannot be reduced to ordinary user Account/Session semantics.

### Government implementations exercise multiple contexts
MOSIP is valuable precisely because registration/proofing, issuance, authentication and partner governance span several CM4DI contexts. Its modules are not ontology modules.

## Remaining Issue #75 work

- inspect authoritative LICENSE for each selected repository before any code/artifact reuse;
- record release/maintenance state and exact repository roles;
- inspect test fixtures/schema/state transitions where concept-bearing;
- map each repository to exact CM4DI CQs and relations;
- distinguish authoritative test suite versus reference implementation versus mature operational platform;
- integrate source coverage with #61/#66 and Gate-D scenario selection.