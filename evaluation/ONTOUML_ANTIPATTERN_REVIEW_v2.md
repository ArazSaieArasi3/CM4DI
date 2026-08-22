# CM4DI Journal V2 — OntoUML / Semantic Anti-Pattern Review

**Wave:** 5 / O15  
**Model:** Gate-C candidate Core and profile interfaces  
**Result:** PASS after corrections documented below.

## Review scope
This pass checks ontological and semantic anti-patterns rather than syntactic OWL problems. It covers rigidity/identity, role modeling, relators, events, contexts, information artifacts, lifecycle, trust and profile contamination.

## Anti-pattern checks

| # | Check | Result | Resolution |
|---:|---|---|---|
| 1 | Universal `Party` superclass over people/orgs/devices/software | PASS | `Party` is abstract `roleMixin`, not identity provider. |
| 2 | `IdentitySubject` as rigid kind | PASS | Reclassified as `roleMixin`; external/profile rigid kinds play it. |
| 3 | Hidden human-only subject assumptions | PASS | Core has no Person-only constraints; P03 explicitly tests Device/Workload/Agent. |
| 4 | Synthetic `MachineIdentity` kind | PASS | Explicitly rejected; machine concepts are profile specializations using Core roles/artifacts. |
| 5 | Subject = DigitalIdentity = Account/Profile | PASS | Three semantic layers are separated; Account/Profile are P01. |
| 6 | Identifier = subject/identity | PASS | Identifier is an information/sign artifact with explicit target/scope relations. |
| 7 | `Evidence` essential-kind overconstraint | **CORRECTED** | Changed `Evidence` and `Proof` to `roleMixin`; credentials/documents/assertions may play the role. |
| 8 | Claim = Attribute = Credential = Evidence | PASS | Separate classes/roles with explicit information-content/evidential relations. |
| 9 | Proof = cryptographic proof only | PASS | Core Proof is evidential role; cryptographic mechanisms are profiles. |
| 10 | Binding modeled as bare association only | PASS | `IdentityBinding` is a relator with mediation and evidence grounding. |
| 11 | Authentication = proofing | PASS | Separate events and CQs. |
| 12 | Enrollment = Provisioning | PASS | Enrollment in Core; Provisioning P01. |
| 13 | AuthenticationResult = Session | PASS | Session P01 with independent lifecycle. |
| 14 | Authorization decision = durable grant | PASS | `AuthorizationResult` separate from `AccessGrant` relator. |
| 15 | Principal = Person | PASS | Principal is `roleMixin`; may be account/group/workload/person representation. |
| 16 | IAM Role = UFO Role | PASS | IAM roles normalize to PermissionBundle in P01; UFO Role used only ontologically. |
| 17 | Resource as one rigid artifact kind | PASS | Resource is heterogeneous `roleMixin`. |
| 18 | Delegated actor = represented/authorizing subject | PASS | `Delegation` relator preserves delegator/delegatee; actor/subject may differ. |
| 19 | IdentityContext = AuthorizationContext | PASS | Separate `situation` classes and CQs. |
| 20 | IdentityContext = Tenant/Realm/TrustDomain/Audience | PASS | Operational/admin/trust/social contexts are profile/future concepts. |
| 21 | Trust = TrustFramework = TrustAnchor = Certification | PASS | Core `TrustAssessment/TrustReference`; infrastructure/governance in P04. |
| 22 | TrustReference catch-all | PASS | Narrowed to external alignment/reference artifact. |
| 23 | Verifier lexical conflation | PASS | Generic Verifier role retained only with explicit specialized semantics in profiles. |
| 24 | IdentityProvider/CSP as universal rigid actor | PASS | Moved profile-first; neutral interaction/provider roles used instead. |
| 25 | Subscriber as universal subject type | PASS | Moved to NIST/profile mapping. |
| 26 | Credential lifecycle = account/session/participation lifecycle | PASS | Separate profile lifecycles; only generic credential lifecycle in Core. |
| 27 | Status as permanent subtype of Credential | PASS | `CredentialStatus` modeled as dependent mode; no revoked/active rigid subclasses. |
| 28 | Event/object conflation | PASS | Proofing, Enrollment, Authentication, Authorization and lifecycle changes are events; requests/results/claims are artifacts. |
| 29 | Relator truth-maker omission | PASS | IdentityBinding, AccessGrant and Delegation have explicit mediation decisions. |
| 30 | Material relation overuse | **CORRECTED** | Authoritative relation-stereotype overlay identifies mediation/participation/historical/formal relations; first semantic CSV is not authoritative for OntoUML relation stereotypes. |
| 31 | Profile vocabulary contaminates Core | PASS | Four explicit profiles; vendor/protocol/jurisdiction labels do not enter Core. |
| 32 | SSI gravitational pull | PASS | Issuer/Holder/Presentation/Wallet stay P02; Core uses generic credential semantics. |
| 33 | Government/legal identity gravitational pull | PASS | LegalIdentity/PID/certification stay P04. |
| 34 | Social identity conflation | PASS | SocialIdentity/Persona/Reputation remain Social-Future; SocialLogin is P01 mechanism. |
| 35 | AI-agent hype-driven Core promotion | PASS | AI Agent remains P03 profile-first; Core only receives general delegation/principal patterns independently supported elsewhere. |
| 36 | Duplicate `AuthorizationDecision` beside `AuthorizationResult` | PASS | Baseline `AuthorizationResult` is refined; no duplicate class. |
| 37 | Duplicate broad `IdentityEvidence` kind beside evidence-role pattern | PASS | One `Evidence` roleMixin; type/issuer/profile differences are mappings/specializations. |
| 38 | Unqualified assurance scale | PASS | AssuranceAssessment requires dimension + level/value; no universal LoA ladder. |
| 39 | Multiple roots with no identity providers for roleMixins | CONTROLLED | Core roleMixins are intentionally abstract interface types. Each instantiated scenario/profile MUST provide rigid role players. This becomes a profile conformance rule. |
| 40 | Social/organizational Membership duplicated locally | PASS | External reference/profile link only; no social-role ontology duplicated in Core. |

## Constraint checks derived from review

### RoleMixin realization rule
Any concrete instantiation dataset or profile MUST provide a rigid/domain-level role player for `IdentitySubject`, `Party`, `Principal`, `Resource`, `Authenticator`, `Evidence`, `RelyingParty`, and `Verifier` as applicable. Core does not invent one common rigid identity provider.

### Relator completeness rule
- `IdentityBinding` MUST mediate an IdentitySubject and at least one bind target (DigitalIdentity, Credential or Authenticator) and SHOULD be grounded by Evidence where evidence exists.
- `AccessGrant` MUST mediate exactly one Principal and at least one Permission; scope may be represented by Resource/profile scope.
- `Delegation` MUST mediate a delegator and delegatee Principal and SHOULD identify delegated permission/scope.

### Event-result separation rule
- Authentication event → AuthenticationResult record.
- Authorization event → AuthorizationResult record.
- Proofing event → AssuranceAssessment may be produced.
- Credential lifecycle event → Credential/status transition.

No result artifact is substituted for the event occurrence itself.

### Context separation rule
No inference shall equate `IdentityContext`, `AuthorizationContext`, `AdministrativeDomain`, `TrustDomain` or social context merely because a platform uses the word "context", "realm", "tenant" or "domain".

## Remaining formalization cautions — non-blocking
1. `Action` should be reviewed at Wave 7 naming/IRI lock; `ActionSpecification` may be clearer than `Action` while mappings keep the shorter external term.
2. CredentialStatus may be implemented as mode/state plus status information artifact depending on profile; OWL/SHACL should not erase this distinction.
3. Generic Verifier should remain abstract; P02 and authentication mappings must supply specialized verifier semantics.
4. Event-participation and historical-dependence relations should be represented in the native conceptual source where tool support permits; OWL object properties will be operational projections rather than a replacement for UFO semantics.

## Verdict
**PASS.** No unresolved anti-pattern requires reopening Gate B or changing the four-profile architecture. The corrected model is suitable for Gate C review.