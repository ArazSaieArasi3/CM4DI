# CM4DI Journal V2 — Gate B Baseline Gap Matrix

## Purpose
Compare the published/conference CM4DI baseline with the evidence-normalized Gate-B recommendation before any OntoUML/OWL refactor.

## Baseline concepts: retain, refine or reposition

| Baseline concept | Gate-B action | Main issue discovered | Recommended direction for Wave 5 |
|---|---|---|---|
| `Party` | **Refine** | Current usage risks assuming all identity subjects are parties/agents in the same sense; device/workload evidence breaks that assumption. | Ground Party under a broader identity-bearing/entity pattern and separate agency/participation from mere identity-bearing capability. |
| `IdentitySubject` | **Refine materially** | Must support persons, organizations, devices, workloads/software and agents without becoming a rigid taxonomic kind. | Analyze as contextual role/identity-bearing status under UFO. |
| `DigitalIdentity` | **Retain + sharpen** | Boundary against Account, Profile, LegalIdentity and workload/agent identity representations is unclear. | Keep protocol-neutral representation; define identity criterion and representation relation explicitly. |
| `IdentityContext` | **Retain + narrow** | Used too broadly for tenant/domain/trust/security contexts. | Keep semantic interpretation scope; separate AuthorizationContext, AdministrativeDomain and TrustDomain. |
| `Identifier` | **Retain** | Scheme-specific identifiers may tempt Core proliferation. | Keep generic identifier; DID/SPIFFE ID/Pseudonym become profile specializations/mappings. |
| `IdentityAttribute` | **Retain + strengthen** | Provenance, binding and quality/confidence are under-modeled. | Add provenance/binding pattern; keep detailed assurance dimensions explicit. |
| `Claim` | **Retain + redefine** | Protocols use `claim` for both name/value token members and semantic assertions. | Define ontology-level assertion about subject; protocol syntax maps to it. |
| `Credential` | **Retain + categorize** | Current breadth risks conflating VC, device cert, SVID, access token and temporary credential. | Retain generic credential and profile categories/lifecycles. |
| `Authenticator` | **Retain** | Device can be identity-bearing and must not be reduced to authenticator. | Preserve authenticator function and explicitly separate Device. |
| `Authentication` | **Retain + separate** | Proofing, federation and session can be conflated with authentication. | Keep authentication event/process with evidence/method/context/result. |
| `AuthenticationResult` | **Retain** | Not equivalent to Session. | Keep result; Session in profile. |
| `Authorization` | **Retain + expand minimally** | Lacks explicit principal, resource, action, request/context and permission/grant semantics. | Add minimal authorization semantic kernel without importing full access-control ontology. |
| `AuthorizationResult` | **Refine** | `result` lacks explicit decision semantics. | Define decision outcome (permit/deny etc.) in current result rather than duplicate unless model analysis requires subtype. |
| `IdentityProvider` | **Reposition/redefine** | Federation IdP, broader identity service provider and authoritative identity source are not equivalent. | Narrow to contextual federation/authentication provider role; source/provider abstractions in profiles. |
| `CredentialServiceProvider` | **Reposition** | NIST-centric and not universal issuer abstraction. | Introduce neutral Issuer role; retain CSP as profile/mapping where needed. |
| `Verifier` | **Refine/split semantics** | Authentication verifier and VC presentation verifier differ. | Use contextual verifier pattern plus explicit specialized roles. |
| `RelyingParty` | **Retain but remodel as role** | Current rigid/subkind interpretation is ontologically weak. | Anti-rigid contextual role played by organization/software/service. |
| `Subscriber` | **Profile/deprecate from minimal Core candidate** | NIST-centric; Holder, Applicant and Account-holder semantics do not align cleanly. | Keep as NIST mapping/profile role unless a generic subscription relation is independently required. |
| `Enrollment` | **Retain/review** | Enrollment differs from proofing, provisioning, registration and ecosystem participation. | Define enrollment precisely and prevent lifecycle conflation. |
| `TrustReference` | **Retain as lightweight reference hook** | Risk of becoming catch-all for framework, registry, anchor, trust and evidence. | Keep reference/alignment object only; first-class trust/governance constructs live in profile. |
| `ONTrust:Trust` | **Retain external alignment** | Must not be used as substitute for certification, registry status or cryptographic validation. | Preserve trust relation/assessment alignment and separate institutional/technical trust constructs. |

## New Core semantic gaps recommended for admission

| New Core candidate | Evidence convergence | Why baseline is insufficient |
|---|---|---|
| Identity-Bearing Entity pattern | standards + non-human + IAM | Current Party/IdentitySubject structure does not cleanly support device/workload/agent cases. |
| Identity Evidence | NIST/OpenID + academic + attestation | Evidence currently exists only as helper references and cannot support proofing/assurance semantics. |
| Identity Proofing | NIST + government + academic | Baseline jumps from attributes/claims to enrollment/authentication without identity-establishment event semantics. |
| Evidence/Proof pattern | W3C/WebAuthn + academic + SPIFFE | Claim/Credential alone cannot represent supporting/cryptographic proof material. |
| Attribute Provenance | government + IAM | Source/authority/derivation is necessary for semantic trust in attributes. |
| Attribute/Identity Binding | government + attestation | `aboutSubject` is weaker than evidence-backed binding. |
| Credential Status/Lifecycle | VC/OpenID + academic + machine credential rotation | Status and lifecycle are only fields/references, not coherent event/state semantics. |
| Resource | XACML/AuthZEN/OAuth + IAM | Authorization has no target entity. |
| Action | XACML/AuthZEN/OAuth + IAM | Authorization has no explicit requested operation. |
| Authorization Request | XACML/AuthZEN | Request input is not the event itself. |
| Authorization Context | standards + Conditional Access | Runtime environmental context is not IdentityContext. |
| Principal | AWS/Entra/Google/Kubernetes + non-human | Authorization cannot remain human/RP-centric. |
| Permission | IAM + authorization standards | Roles/scopes/policies need a neutral minimal authorization unit. |
| Access Grant | cloud IAM + RBAC/OAuth patterns | Durable entitlement assignment differs from runtime authorization decision. |
| Delegation / actsOnBehalfOf | OAuth token exchange + AI agents + literature | Actor and subject must be separately representable. |
| Assurance Assessment | NIST/ISO + UK/Canada | Baseline assurance hints cannot represent different proofing/authentication/attribute confidence dimensions. |
| Role-in-Interaction pattern | academic + VC/federation/IAM | Current actor classes risk rigidity and duplicated role taxonomies. |

## High-value concepts deliberately kept out of Core

| Candidate family | Gate-B disposition | Reason |
|---|---|---|
| Account/Profile/Directory/Provisioning/Session | Enterprise/Federation Profile | Highly recurrent operational semantics but not universal across paradigms. |
| Federation/Assertion/Broker | Enterprise/Federation Profile | Paradigm-specific interaction architecture. |
| Issuer/Holder/Presentation/Wallet/Controller | Wallet/VC Profile | Essential to VC/wallet ecosystems but should not recenter Core on SSI. |
| TrustFramework/Registry/TrustedList/Anchor/GovernanceAuthority | Trust/Assurance/Government Profile | First-class, but institutional/cryptographic trust architecture is profile scope. |
| LegalIdentity/PID/government attestations | Government Profile | Human/legal identity substrate is incompatible with universal non-human Core semantics. |
| Workload/ServiceAccount/Device/Attestation/AI Agent | Machine/Workload/Device/Agent Profile | Strong evidence, but entity taxonomy and lifecycle are domain-specific. |
| SocialIdentity/Persona/Reputation/Salience | Social-Future | Different psychosocial research object; explicit scope exclusion. |

## Field-registry implications
The v0.1 field registry remains a useful baseline but cannot be treated as final Core after Gate B. Specific fields requiring review include:
- `partyType`, `subjectCategory`: currently encode taxonomy as codes where explicit ontology categories/roles may be required;
- `homeContextRef`: must not silently absorb administrative/trust domains;
- `providerType`: risks collapsing service/provider roles;
- `requestedScopeRef`: must align with explicit Resource/Action/Permission semantics;
- `verifierType`: should not hide distinct verifier roles in a string code;
- `representationType`: should not make Account/VC/token categories mere string values when profile modeling requires explicit types;
- `trustFrameworkName`: demonstrates why TrustReference must remain a hook rather than substituting for a TrustFramework entity;
- `attributeSourceRef` and `confidenceLevel`: require stronger provenance/assurance patterns;
- `statusReference`, `lifecycleStatus`: require explicit typed lifecycle semantics rather than only datatypes.

## Gate-B baseline conclusion
The conference model is a valid minimal starting point, but Journal V2 requires a **targeted semantic expansion plus ontological role correction**, not a wholesale replacement. The highest-value work is not adding every discovered term: it is correcting identity-bearing/role boundaries, adding evidence/proofing and minimal authorization semantics, strengthening lifecycle/provenance/assurance, and moving paradigm-specific constructs into four governed profiles.
