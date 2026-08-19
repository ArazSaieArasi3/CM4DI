# CM4DI Journal V2 — Standards Semantic Ambiguities and Collisions

**Purpose:** prevent lexical similarity across standards from causing ontological conflation.

## High-priority collisions

| Term | Different standard uses | Risk to current CM4DI | Preliminary treatment |
|---|---|---|---|
| **Verifier** | NIST authentication verifier; W3C VC verifier; ISO mdoc verifier/reader | Current `Verifier` can incorrectly imply these are one ontological role | Keep lexical term under review; likely introduce qualified role subtypes or redefine a neutral verification role |
| **Credential** | NIST authentication credential/binding context; W3C VC claims-bearing verifiable credential; WebAuthn public-key credential; OAuth tokens sometimes colloquially called credentials | One class can become semantically overloaded | Preserve a neutral CM4DI definition and map ecosystem-specific credential types explicitly; do not equate access token with credential by default |
| **Assertion** | SAML/NIST federation assertion; WebAuthn authentication assertion | Same label denotes different artifacts and evidentiary functions | Separate `FederationAssertion` from `AuthenticationAssertion`; examine generic supertype only if ontologically sound |
| **Claim** | JWT/OIDC name-value member; VC assertion about a subject; ordinary-language claim; current CM4DI social object asserting attributes | Protocol syntax can collapse into semantic assertion | Keep CM4DI Claim definition conceptual; add explicit mappings from protocol claims rather than adopting name/value semantics |
| **Subject** | Identity subject; JWT subject identifier referent; authorization subject/principal; DID subject; credential subject | A subject may be bearer of identity, target of claim, authorization principal, or identifier referent | Use role/context distinctions; avoid one unconstrained `Subject` class |
| **Subscriber** | NIST role after enrollment; general service subscriber in ordinary systems | Current CM4DI role may be over-generalized | Treat NIST Subscriber as strong evidence for an enrollment/authentication role, but test whether Core needs a more neutral role |
| **Holder** | VC/ISO mdoc party controlling/possessing credential; may differ from credential subject | Equating Holder with Subscriber or IdentitySubject loses holder-subject distinction | Wallet/VC profile role; explicit `holds` and subject relation |
| **Controller** | DID/controlled-identifier controller; software/admin controller in other ecosystems | Can be confused with data controller or system administrator | Keep identifier-control meaning scoped to Wallet/VC profile unless broader evidence justifies abstraction |
| **Identity Provider** | OIDC OP/IdP; NIST provider functions; enterprise IdP; wallet-based federation may distribute functions | Current rigid subkind may not fit contextual provider participation | Revisit whether provider categories are roles played by organizations/software/services rather than rigid Party subkinds |
| **Relying Party** | OIDC RP; NIST RP; WebAuthn RP; VC verifier sometimes functionally relies on data | Related but not identical scopes | Preserve neutral reliance semantics and specialize/mapping by protocol |
| **Evidence / Proof** | NIST Identity Evidence; VC cryptographic proof; WebAuthn attestation/assertion; documentary evidence | A single `Evidence` class can mix proofing evidence with cryptographic proof | Introduce explicit evidence taxonomy only after UFO analysis |
| **Context** | CM4DI IdentityContext; NIST assurance/risk context; AuthZEN/XACML authorization context; WebAuthn RP/origin scope | Reusing IdentityContext for all contexts would be a category error | Keep `IdentityContext` distinct; introduce `AuthorizationContext`/other scoped contexts if justified |
| **Status** | credential status/revocation; party account status; role status; session status | Generic string status fields can hide state semantics | Model lifecycle/state per bearer; do not create one universal status enumeration |
| **Token** | ID Token; Access Token; Refresh Token; Security Token; VC token-form representations | Tokens carry different authority/identity semantics | Mapping artifact family; no generic Token Core class unless later evidence shows clear ontological identity |

## Structural ambiguity found in Authorization

The current CM4DI `Authorization` event evaluates claims and produces an `AuthorizationResult`. Across ISO/IEC 29146, XACML 3.0 and OpenID AuthZEN, however, an access decision is consistently structured around at least:

- a **Subject/Principal**;
- a **Resource**;
- an **Action**;
- a **Context/Environment** (optional or contextual);
- a **Decision**;
- often a **Policy/PDP/PEP** architecture.

This is not yet a model change, but it is a **high-confidence gap finding** to take to Gate B.

## Structural ambiguity found in proofing/enrollment

NIST Revision 4 distinguishes an applicant presenting **identity evidence**, an **identity proofing** process, and subsequent/associated **enrollment**. CM4DI currently has `Enrollment` but no first-class `IdentityEvidence` or `IdentityProofing`. Treating Enrollment as covering all three would erase meaningful lifecycle distinctions.

## Structural ambiguity found in federation

NIST, SAML, OIDC and OpenID Federation jointly distinguish:

- authentication at a provider;
- federation relationships;
- assertions/ID tokens conveyed to a relying party;
- metadata/entity configuration;
- trust chains/trust anchors/policy in multilateral federation.

CM4DI currently has IdP/RP and `TrustReference`, but lacks a first-class federation semantic structure. Gate B must decide which part belongs in Core and which part belongs in Enterprise/Federated and Trust profiles.

## Decision rule

No collision above is resolved by renaming alone. Resolution requires:
1. identity criteria and ontological category analysis;
2. mapping of each standard usage to that concept;
3. tests against competency questions and scenarios;
4. a Gate B Core/Profile/Deferred/Reject decision.