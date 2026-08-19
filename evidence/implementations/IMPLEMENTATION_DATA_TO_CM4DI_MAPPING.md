# CM4DI Journal V2 — Implementation/Data-to-CM4DI Mapping

**Status:** discovery/evaluation decision support; no Gate-B admission yet.  
**Review date:** 2026-08-19

## Evidence roles

The artefacts in Issue #7 play three different roles and must not be conflated:

1. **Conformance evidence** — official test suites state/encode expected behaviors for standards implementations.
2. **Operational implementation evidence** — real software exposes concrete actors, records, events, state transitions and integration boundaries.
3. **Empirical instantiation evidence** — datasets provide event/attribute instances suitable for mappings, competency questions and scale tests.

## Mapping matrix

| Artefact | CM4DI targets | Relations/events tested | Evaluation use | Main semantic safeguard |
|---|---|---|---|---|
| W3C VC 2.0 test suite | Credential, Claim, Holder, Issuer, Verifier, CredentialSubject, CredentialStatus | issues, holds, presents, verifies/evaluates, hasStatus | Wallet/VC mapping coverage + CQs | VC `Verifier` remains profile role; do not merge with NIST authenticator verifier |
| W3C DID test suite | Identifier, IdentitySubject, Controller, VerificationMethod | identifies, controlledBy, resolvesTo/represents | Identifier/controller mapping | DID is an Identifier specialization/profile, not a new Core identity paradigm class |
| VC status test suite | CredentialStatus, lifecycle event/state | status changes, suspension/revocation checks | Credential lifecycle CQ design | mechanism-specific bitstring remains profile-level |
| OpenID conformance suite | RP/Client, Provider, SubjectIdentifier, Assertion/Token, Federation, Authorization Request/Result | authenticates, issues token/assertion, reliesOn, requests/authorizes | Enterprise/Federated interoperability mapping | token/protocol artefact ≠ Credential/Claim by lexical similarity alone |
| EUDI Wallet reference implementation | Wallet, Holder/User, PID/Attestation provider, RP/Verifier, Credential/Attestation, Presentation | issuance, storage/holding, presentation, verification, disclosure | Cross Government + Wallet/VC scenario | Wallet implementation objects do not define Core classes |
| SPIRE | Workload, SPIFFE ID, SVID, Attestation, TrustDomain, TrustBundle | attests, assigns identifier, issues credential, federates trust domain | Machine/workload scenario + CQs | Workload ≠ WorkloadIdentity ≠ Identifier ≠ SVID; TrustDomain ≠ TrustFramework |
| Keycloak | Account/Profile, Realm, Client/Application, IdP/Broker, Session, Group, Permission/Role constructs | broker/federate, authenticate, maintain session, assign access | Enterprise operational scenario | Realm ≠ IdentityContext; IAM Role ≠ UFO Role; User Federation ≠ federation authentication |
| MOSIP reference implementation | Resident/Subject, Registration, Credential, Authentication, Partner/RP, Provider | register, issue, authenticate, onboard partner | Foundational/government lifecycle scenario | implementation module names remain Government-profile mappings |
| LANL authentication dataset | Account/user proxy, Computer/Resource, Authentication event, timestamp | authenticatesTo at time | event-graph instantiation, temporal/scale CQs | user IDs are anonymized technical identifiers, not evidence of LegalIdentity/Person subtype |
| RBA dataset | Account, AuthenticationAttempt, AuthenticationResult, Device/ClientContext, Location/NetworkContext, Risk indicator | attempts authentication, succeeds/fails, observedIn context | CQ/query evaluation with success/failure and context | synthesized feature values; attack labels are evaluation annotations, not identity concepts |
| ID4D 2025 | Government ID System, Credential capability, Digital-ID availability, RemoteAuthentication capability, country/context | system provides capability; population has/accesses ID | Government-profile contextual queries | national aggregates are not transaction/individual identity events |
| Global Findex 2025 | Person/respondent, ID ownership/use, digital-ID access/use, contextual attributes | person reports possession/use/access | optional person-level Government-profile examples | survey response ≠ proofing/authentication assurance evidence |

## High-value competency-question families enabled by this wave

### CQ-IMPL-01 — Cross-paradigm credential semantics
Can CM4DI represent issuance, holding/presentation and verification of a VC/EUDI credential without treating protocol artefacts as Core identity concepts?

### CQ-IMPL-02 — Authentication trace
Can a user/account authenticate to a resource/computer at a time, and can repeated events be represented without conflating Account with IdentitySubject?

### CQ-IMPL-03 — Contextual authentication result
Can CM4DI distinguish an authentication attempt, its result and contextual evidence such as device/network/location characteristics?

### CQ-IMPL-04 — Workload identity binding
Can CM4DI represent that a workload is attested, is assigned an identifier, and receives an SVID credential within a trust domain?

### CQ-IMPL-05 — Federation/brokering
Can an account/subject be represented through an external identity source/IdP while a local IAM system maintains its own account/profile and session?

### CQ-IMPL-06 — Government digital-ID capability
Can a jurisdiction/system be represented as providing an official/digital credential and remote authentication capability without claiming that every resident has or uses it?

### CQ-IMPL-07 — Lifecycle separation
Can credential revocation, account/session termination, provider participation status and workload credential rotation be represented as different lifecycle domains?

## Candidate implications for Gate B

Implementation/data evidence strongly reinforces, but does not yet admit:
- `Account` / local identity representation;
- `AuthenticationAttempt` distinct from `AuthenticationResult`;
- `Session` distinct from authentication;
- generic `Evidence/Attestation` and `IdentityBinding` patterns;
- `Principal` as contextual authorization role;
- generic credential/status lifecycle semantics;
- `Delegation/actsOnBehalfOf` where operational scenarios require actor/subject separation.

It also reinforces keeping the following profile/mapping-first:
- DID-specific controller/document constructs;
- Wallet implementation objects;
- SPIFFE TrustDomain/TrustBundle/SVID specializations;
- Realm/tenant product constructs;
- national-ID platform modules.

## Gate-D handoff

After Gate B/C fixes the ontology, each selected scenario should receive:
- a deterministic input/sample or versioned test vector;
- a mapping file from source fields/objects to CM4DI IRIs;
- one or more competency questions and SPARQL queries;
- expected result/assertion;
- provenance and version metadata;
- a pass/fail result recorded by CI where technically feasible.