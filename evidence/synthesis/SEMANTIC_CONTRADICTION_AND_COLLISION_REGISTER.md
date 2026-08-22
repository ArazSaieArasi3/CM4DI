# CM4DI Journal V2 — Semantic Contradiction and Collision Register

## Purpose
This register records cross-stream semantic collisions that must be resolved during Wave 5 conceptual modeling. A collision is not automatically an error in a source; it indicates that the same label is used for different ontological categories, or different labels refer to related but non-equivalent constructs.

| ID | Collision | Resolution for Gate B | Wave-5 implication |
|---|---|---|---|
| COLL-01 | `IdentitySubject` vs human-only assumptions | IdentitySubject must support human and non-human bearers. Do not make Person the hidden superclass. | Revisit UFO status of Party/IdentitySubject and introduce/align broader identity-bearing entity pattern. |
| COLL-02 | `Party` vs Device/Workload | A device/workload can be identity-bearing without necessarily being a social/agentive Party in the same sense. | Separate foundational bearer from contextual participation/agency. |
| COLL-03 | `DigitalIdentity` vs `Account` vs `Profile` | DigitalIdentity remains generic representation; Account/Profile are profile-level specializations/records. | Define identity criteria and representation relations explicitly. |
| COLL-04 | `DigitalIdentity` vs `LegalIdentity` | LegalIdentity is a government/legal substrate, not a synonym of DigitalIdentity. | Keep LegalIdentity in Government profile. |
| COLL-05 | `Principal` vs `IdentitySubject` | Principal is an authorization-context role; the principal may be a subject, account, group or workload representation. | Model Principal as anti-rigid contextual role. |
| COLL-06 | IAM `Role` vs UFO `Role` | Vendor IAM roles/permission sets are permission bundles or grants, not UFO roles by label. | Introduce PermissionBundle mapping and preserve UFO role semantics. |
| COLL-07 | `Issuer`, `Holder`, `Verifier`, `RelyingParty` actor classes | These are generally contextual interaction roles and may be played by different underlying entities. | Replace rigid classification where necessary with role pattern. |
| COLL-08 | Authentication `Verifier` vs VC presentation `Verifier` | Same label, different interaction semantics. | Generic verifier pattern only with explicit specialized roles. |
| COLL-09 | `IdentityProvider` vs `IdentityServiceProvider` vs `IdentitySource` | Provider authenticating/federating is not necessarily the authoritative source of profile/attribute data. | Narrow federation IdP semantics; model source/provider roles separately in profiles. |
| COLL-10 | `CredentialServiceProvider` vs Issuer | CSP is NIST-centric and cannot serve as universal issuer abstraction. | Introduce neutral Issuer role; retain CSP as profile/mapping if needed. |
| COLL-11 | `Credential` vs Token vs SVID vs temporary cloud credential | These are credential-like artifacts with different purposes/lifecycles. | Keep generic Credential in Core and profile-specific categories. |
| COLL-12 | `Evidence` vs `Proof` vs `Assertion` vs `Claim` | Evidence supports; Proof demonstrates/verifies; Claim asserts; Assertion is overloaded across federation/WebAuthn. | Build neutral Evidence/Proof/Claim pattern; keep ambiguous Assertion mostly profile-specific. |
| COLL-13 | Federation Assertion vs WebAuthn Assertion | Identical word denotes information statement vs authenticator-generated proof material. | Do not create an unqualified universal `Assertion` solely from lexical overlap. |
| COLL-14 | Identity Proofing vs Authentication | Proofing establishes confidence in a claimed identity; authentication verifies control/association at access time. | Separate events, evidence and results. |
| COLL-15 | Authentication Result vs Session | Successful authentication can establish a session, but result and temporally extended session are not identical. | Session remains profile-level with independent lifecycle. |
| COLL-16 | Authorization Decision vs Access Grant | Runtime permit/deny is not a durable assignment of permissions. | Keep AuthorizationResult/Decision separate from AccessGrant. |
| COLL-17 | `IdentityContext` vs AuthorizationContext | Identity interpretation context differs from runtime decision environment. | Preserve distinct context constructs. |
| COLL-18 | `IdentityContext` vs Tenant/Realm/AdministrativeDomain | Technical administrative partitions are not automatically identity semantic contexts. | AdministrativeDomain in Enterprise profile. |
| COLL-19 | `IdentityContext` vs SPIFFE TrustDomain | TrustDomain is an identity namespace/security boundary backed by trust material, not generic identity context. | TrustDomain in Machine/Trust profile. |
| COLL-20 | Trust relation vs TrustFramework | A trust relation/assessment is not a governed rule system. | ONTrust alignment for trust; TrustFramework profile construct. |
| COLL-21 | TrustFramework vs TrustRegistry/TrustedList | Framework defines governance/rules; registry/list records participant/service status. | Separate classes/relations in Trust profile. |
| COLL-22 | TrustAnchor vs TrustRegistry | Cryptographic/authoritative validation root is not a registry/list. | Separate TrustAnchor/Chain from governance registry. |
| COLL-23 | TrustDomain vs TrustFramework | SPIFFE-style security namespace differs from institutional/government trust framework. | Bridge in Trust profile; never synonymize. |
| COLL-24 | Reputation vs Trust/Assurance | Reputation is aggregated social evaluation; assurance is evidence-based confidence; trust is relational/assessment semantics. | Reputation goes Social-Future. |
| COLL-25 | Group in IAM vs Group Identity | Access group is a collection/assignment construct; group identity is psychosocial self-concept. | Enterprise Group stays profile; GroupIdentity Social-Future. |
| COLL-26 | Membership/Affiliation vs IdentityAttribute | Membership can be represented as claim/attribute content, but social/organizational membership has independent relational semantics. | Link/reference external ORG/social ontology where needed. |
| COLL-27 | Persona vs Account/Profile | Persona is curated/performative self-presentation; profile/account is a technical record/representation. | Persona Social-Future. |
| COLL-28 | Identity Salience vs IdentityContext | Salience is psychological prominence; context is semantic/operational scope. | Salience Social-Future. |
| COLL-29 | Self-Disclosure vs Credential Presentation | Social disclosure behavior is not protocol-level credential/attribute presentation. | Social-Future with bridge only. |
| COLL-30 | Device vs DeviceIdentityRecord vs DeviceCredential vs Authenticator | Physical/virtual device, registry representation, credential and authenticator function are separate. | Device profile must model all four explicitly. |
| COLL-31 | Workload vs WorkloadIdentity vs ServiceAccount vs Principal | Runtime entity, identity representation/account and authorization role are distinct. | Machine profile composes Core DigitalIdentity/Account/Principal rather than `MachineIdentity` catch-all. |
| COLL-32 | Service vs ServicePrincipal | Service may denote capability/software; ServicePrincipal is a platform-local security representation. | Avoid universal ServicePrincipal Core class. |
| COLL-33 | AI Agent vs AgentIdentity | Agent is an agentive software entity; AgentIdentity is its representation/account. | Agent profile only until conceptual maturity improves. |
| COLL-34 | Credential lifecycle vs Account lifecycle vs Session lifecycle vs Ecosystem-participation lifecycle | Similar state labels do not imply one lifecycle object. | Use generic lifecycle pattern with typed target domains; do not merge states mechanically. |
| COLL-35 | Provisioning vs Enrollment vs Participant Registration | Provisioning creates/synchronizes technical representations; enrollment establishes subject/provider relationship; participant registration establishes ecosystem eligibility. | Separate profile processes with only generic lifecycle/event reuse. |
| COLL-36 | Policy vs Group Norm | Access/governance policy is not social norm by label. | GroupNorm Social-Future; detailed Policy remains profile-level. |
| COLL-37 | Social Login vs Social Identity | Social Login is external-IdP federation/authentication; Social Identity is psychosocial selfhood. | Keep Social Login in Enterprise/Federation profile and Social Identity outside CM4DI. |
| COLL-38 | Paradigm/Ecosystem vs ontology entity | Centralized/federated/SSI/government/workload are analysis/profile dimensions, not necessarily domain individuals/classes. | Keep as research/mapping metadata. |

## Exit rule
No Wave-5 class or relation may be added merely because two source terms share a label. Candidate admission must preserve the distinctions above and be justified by competency questions plus UFO analysis.
