# CM4DI Journal V2 — UFO / OntoUML Stereotype Review

**Wave:** 5 / O14  
**Status:** PASS with two model corrections applied before Gate C  
**Reference vocabulary:** OntoUML official vocabulary (`https://w3id.org/ontouml`) and OntoUML Community Portal.

## Review principles
- `roleMixin` is used for anti-rigid relationally dependent types whose instances may follow different identity principles.
- `role` is used for an anti-rigid relational specialization of a single identity provider.
- `relator` is used for truth-makers of material relations and mediates its relata.
- `situation` represents a configuration of entities understood as a whole.
- `event` is used for perdurants/process occurrences.
- `kind` is used only where the modeled information/social artifact supplies a coherent identity principle within the conceptual scope.

## High-impact correction discovered during review
The first draft classified `Evidence` as a `kind`. This is too restrictive because a Credential, document, record, assertion, runtime attestation artifact, or other information artifact can **play the evidence role** without changing its own identity principle. Therefore:

- `Evidence` → **`<<roleMixin>>`**
- `Proof` → **`<<roleMixin>>` specialization of Evidence**

This preserves the Gate-B requirement that Evidence/Proof are semantically distinct from Claim/Credential while avoiding the false claim that every evidence item belongs to one essential artifact kind.

## Class review

| Concept | Candidate stereotype | Result | Rationale / control |
|---|---|---|---|
| Party | `<<roleMixin>>` | PASS | Contextual participant; organizations/software/people may play it. Must remain abstract/interface-like in Core. |
| IdentitySubject | `<<roleMixin>>` | PASS | Human/non-human neutral subjecthood is anti-rigid and heterogeneous. Profile/domain kinds provide identity principles. |
| DigitalIdentity | `<<kind>>` | PASS | Managed representation artifact has an artifact-level identity independent from its subject. |
| Identifier | `<<kind>>` | PASS with definition control | Identifier is treated as an information/sign artifact; identification is represented by relation, not lexical value equality. |
| IdentityContext | `<<situation>>` | PASS | Context is modeled as a configuration relevant to interpretation, avoiding confusion with tenant/realm/domain objects. |
| IdentityAttribute | `<<kind>>` information object | PASS with scope control | Represents identity information, not necessarily the intrinsic UFO quality of the subject. This avoids datatype/quality conflation. |
| Claim | `<<kind>>` information object | PASS | A proposition/assertion artifact has its own identity/provenance. |
| Evidence | `<<roleMixin>>` | **CORRECTED / PASS** | Evidence is a contextual use role that heterogeneous artifacts can play. |
| Proof | `<<roleMixin>>` | **CORRECTED / PASS** | Specialized evidence-use role; cryptographic proof types remain P02/P03. |
| IdentityBinding | `<<relator>>` | PASS | Truth-maker for material subject↔representation/authenticator binding relations. |
| Credential | `<<kind>>` information object | PASS | Issued artifact identity is distinct from subject and holder. Credential may additionally play Evidence/Proof roles. |
| CredentialStatus | `<<mode>>` | PASS provisional | Status is modeled as a dependent mode of Credential; profile-specific status assertions/registries may reify it differently in OWL. |
| CredentialLifecycleEvent | `<<event>>` | PASS | Lifecycle change occurrence. |
| CredentialIssuance | `<<event>>` | PASS | Event subtype establishing issued credential(s). |
| IdentityProofing | `<<event>>` | PASS | Evidence-evaluation occurrence/process; not a type of Authentication. |
| Enrollment | `<<event>>` | PASS | Establishes managed representation/binding; not Provisioning. |
| Authentication | `<<event>>` | PASS | Verification occurrence/process. |
| Authenticator | `<<roleMixin>>` | PASS | Device/key/secret/other artifacts with different identity principles can play this role. |
| AuthenticationResult | `<<kind>>` information object | PASS | Result record/representation is distinct from the event and from Session. |
| AssuranceAssessment | `<<kind>>` information object | PASS | Reified assessment supports dimension/value/provenance and avoids one overloaded LoA class hierarchy. |
| Authorization | `<<event>>` | PASS | Evaluation occurrence producing decision/result. |
| AuthorizationRequest | `<<kind>>` information object | PASS | Request artifact distinct from evaluation event. |
| AuthorizationContext | `<<situation>>` | PASS | Environmental/request configuration, explicitly separate from IdentityContext. |
| AuthorizationResult | `<<kind>>` information object | PASS | Decision record preserves traceability and data-set instantiation. |
| Principal | `<<roleMixin>>` | PASS | Humans/accounts/groups/workloads may be principals; anti-rigid authorization context. |
| Resource | `<<roleMixin>>` | PASS | Heterogeneous protected targets can play Resource role. |
| Action | `<<kind>>` description artifact | PASS with naming note | Represents an action specification/type requested for authorization, not the performed event. Formal ontology should consider preferred label `RequestedAction` or `ActionSpecification` if ambiguity persists. |
| Permission | `<<kind>>` normative description | PASS | Normative information artifact; not UFO SocialRole. |
| AccessGrant | `<<relator>>` | PASS | Truth-maker linking Principal, Permission and scope/resource independently of runtime Authorization. |
| Delegation | `<<relator>>` | PASS | Truth-maker for `actsOnBehalfOf`/delegated authority relation with scope. |
| TrustAssessment | `<<kind>>` information object | PASS | Reified assessment artifact; does not replace ONTrust:Trust relation. |
| TrustReference | `<<kind>>` information object | PASS | Alignment/reference artifact only. |
| RelyingParty | `<<roleMixin>>` | PASS | Organizations/software/services can play RP contextually. |
| Verifier | `<<roleMixin>>` | PASS | Generic verification role across heterogeneous players; specialized roles required in profiles. |

## Relation-stereotype review

### Relator mediations — PASS
The following must be realized as `mediation` relations in the final OntoUML model:
- IdentityBinding → IdentitySubject
- IdentityBinding → DigitalIdentity/Credential/Authenticator
- AccessGrant → Principal
- AccessGrant → Permission
- Delegation → delegator Principal
- Delegation → delegatee Principal
- Delegation → delegated Permission/scope when modeled as relator parts

The corresponding convenient domain relations (`boundTo`, `hasGrant`, `actsOnBehalfOf`) are material/derived views whose truth-maker is the relator.

### Event participation — REVISION REQUIRED IN diagram semantics, not class inventory
Relations from events to participants (`IdentityProofing uses Evidence`, `Authentication performedBy`, `Authorization evaluatesRequest`, lifecycle event affects Credential) should be treated as event participation/participation-like relations in OntoUML where supported rather than ordinary undifferentiated material associations.

### Formal/reference relations
- `derivedFrom`, `scopedBy`, `interpretedIn`, `alignsTo` require final relation-stereotype selection during the native OntoUML encoding; they must not be labeled as material merely because they are semantically important.
- The CSV relation registry records conceptual cardinality and semantics first; Wave 7 OWL object properties must follow the Gate-C relation decision record rather than infer stereotypes from CSV relation labels.

## Identity-principle controls
1. Core does **not** define a synthetic `IdentityBearingEntity` kind.
2. `IdentitySubject`, `Party`, `Principal`, `Resource`, `Authenticator`, `Evidence`, `Proof`, `RelyingParty`, and `Verifier` are abstract anti-rigid role interfaces/patterns.
3. Profiles/external domains supply rigid identity providers: Person/Organization, Device, Software/Application, Workload/Runtime entity, information-artifact kinds, etc.
4. A single individual may simultaneously instantiate multiple contextual roles; this must not create co-reference between the roles themselves.

## Gate-C result
**PASS**, provided the corrected `Evidence`/`Proof` stereotypes and relation-stereotype cautions are reflected in the frozen concept/model registries. No blocker requires changing the approved Core/Profile architecture.