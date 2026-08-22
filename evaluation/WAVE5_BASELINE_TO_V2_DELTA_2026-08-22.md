# CM4DI Journal V2 — Conference Baseline → Gate-C Candidate Delta

## Purpose
This is the controlled semantic delta between the published conference model and the journal-v2 conceptual candidate. It is **not** a claim that every added concept becomes a separate OWL class; some are role/relator/event patterns whose formal realization is deferred to Wave 7.

## Executive delta
The conference model was a strong minimal identity/trust conceptual core but mixed several actor labels with entity kinds and under-modeled proofing, provenance, authorization and non-human interoperability. Journal v2 changes the modeling style from actor-class accumulation to an explicit UFO-based separation of **role players, information artifacts, relators, situations and events**.

## Baseline concept treatment

| Baseline | Journal-v2 treatment | Change type | Why |
|---|---|---|---|
| Party | Retained as `<<roleMixin>>` interaction participant | Ontological reclassification | Avoid universal superclass across persons/orgs/devices/software. |
| IdentitySubject | Retained as `<<roleMixin>>` | Ontological reclassification | Allows heterogeneous human/non-human players. |
| DigitalIdentity | Retained; sharpened as managed representation artifact | Definition refinement | Subject ≠ representation; Account/Profile remain profile artifacts. |
| IdentityContext | Retained as contextual situation | Ontological refinement | Prevent Tenant/Realm/TrustDomain/Audience overload. |
| Identifier | Retained as information/sign artifact | Definition refinement | DID/SPIFFE ID become mappings/specializations. |
| IdentityAttribute | Retained as identity-information element | Definition refinement | Avoid assumption that every attribute is an intrinsic quality. |
| Claim | Retained; proposition-level assertion | Semantic normalization | OIDC/JWT field semantics are mappings only. |
| Credential | Retained; lifecycle/provenance strengthened | Semantic enrichment | Supports VC, SVID/device credentials and government attestations without core bias. |
| Authenticator | Retained as heterogeneous `<<roleMixin>>` | Ontological reclassification | Device/key/secret are different kinds. |
| Authentication | Retained as event/process | Clarification | Separated from proofing/federation/session. |
| AuthenticationResult | Retained as result information artifact | Clarification | Explicitly separate from Session. |
| Authorization | Retained but expanded around request/action/resource/principal | Major Core extension | Existing model could not express modern IAM/AuthZEN/XACML scenarios precisely. |
| AuthorizationResult | Retained and strengthened as explicit decision record | Definition refinement | Avoid duplicate AuthorizationDecision class. |
| Enrollment | Retained as event | Clarification | Separated from IdentityProofing and Provisioning. |
| RelyingParty | Retained as `<<roleMixin>>` | Ontological reclassification | RP is contextual, not a rigid kind. |
| Verifier | Retained only as generic role pattern | Semantic split | Authentication verifier ≠ credential presentation verifier. |
| IdentityProvider | Profile-first contextual provider/federation role | Core → Profile | IdP semantics are federation/protocol biased. |
| CredentialServiceProvider | Profile/mapping; use neutral issuer role pattern | Core → Profile | CSP is NIST-centric and not universal. |
| Subscriber | Profile/mapping | Core → Profile | NIST subscription relationship is not universal identity semantics. |
| TrustReference | Retained only as external-alignment/reference artifact | Major narrowing | Must not be catch-all for TrustFramework/Registry/Anchor/Certification. |
| ONTrust:Trust | External alignment retained | No local redefinition | Preserve modular trust grounding. |

## New Core semantic patterns
1. Evidence and Proof distinction.
2. IdentityProofing.
3. IdentityBinding as a relator.
4. Attribute/evidence provenance.
5. CredentialStatus and generic CredentialLifecycleEvent.
6. CredentialIssuance.
7. AssuranceAssessment with explicit dimension.
8. Principal contextual role.
9. Resource contextual role.
10. Action specification.
11. AuthorizationRequest.
12. AuthorizationContext distinct from IdentityContext.
13. Permission.
14. AccessGrant as relator.
15. Delegation/actsOnBehalfOf as relator.
16. TrustAssessment distinct from TrustReference/governance infrastructure.
17. Systematic Role-in-Interaction pattern for RP/Verifier and profile roles.

## Explicitly not promoted to Core
- Account / UserProfile / Directory / IdentitySource
- Federation / Broker / Provisioning / Session / IAM Role bundle
- Issuer / Holder / Wallet / VC Presentation / Controller / DID Registry
- TrustFramework / TrustRegistry / TrustAnchor / Certification / LegalIdentity
- Workload / Device / ServiceAccount / SPIFFE / AI Agent
- SocialIdentity / Persona / Reputation

These concepts remain first-class in their profiles where required; exclusion from Core is not exclusion from CM4DI journal scope.

## Structural benefits
- Removes human-only assumptions.
- Removes NIST/OIDC-specific provider taxonomy from universal Core.
- Explains cloud IAM principals and machine identity without lexical hacks.
- Makes subject/representation/account distinctions explicit.
- Separates durable grant from runtime authorization decision.
- Separates proofing from authentication and provisioning.
- Separates trust assessment from institutional conformance and cryptographic trust anchors.
- Supports executable CQs and later SHACL/SPARQL evaluation.

## Regression protection
The published conference `CM4DI.owl` and draw.io model remain immutable. Journal-v2 model artifacts are stored under `model/journal-v2/` and can evolve until Gate C approval.