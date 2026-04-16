# CM4DI Field Registry v0.1

## Purpose

This document defines the **canonical field registry** for the current core version of **CM4DI**.

Its purpose is to identify a **minimal but sufficient ontology-level field set** for each class in the current CM4DI model so that the ontology can function as a usable **core ontology**, while avoiding premature overload with syntax-specific, vendor-specific, or profile-specific fields.

This version follows the following principles:

- only **canonical and stable** fields are included in the core
- fields must support **conceptual reasoning**, **traceability**, and **cross-standard alignment**
- syntax-level and framework-specific fields are deferred to **profile layers**
- the registry is designed to support future mappings to:
  - OpenID Connect (OIDC)
  - W3C Verifiable Credentials (VC)
  - Amazon IAM
  - Microsoft Identity Platform

---

## Field Selection Rules

A field is included in the CM4DI core registry if it satisfies most of the following conditions:

1. it has a stable meaning at the ontology level
2. it is useful across more than one ecosystem or standard
3. it supports reasoning, traceability, interoperability, or scenario instantiation
4. it does not overfit the ontology to one syntax, token format, protocol, or vendor
5. it contributes to making the class independently usable inside the current CM4DI core

---

## Status Values

- **Core**: should be represented in the current CM4DI core
- **Profile**: useful, but should be represented in a profile layer rather than in the current core
- **Deferred**: intentionally postponed for later versions

---

## 1. Identity-Bearing Entities

### `Party`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `partyId` | Identifier | `1` | Core | Stable identifier of the base participating entity. | Primary anchor for all party instances. |
| `partyType` | Code / String | `1` | Core | General type of the party. | Examples: person, organization, service, software agent. |
| `displayName` | String | `0..1` | Core | Human-readable label for the party. | Useful for display, documentation, and UI. |
| `status` | Code | `0..1` | Core | Current status of the party. | Examples: active, suspended, inactive, archived. |
| `description` | String | `0..1` | Deferred | Descriptive textual summary of the party. | Can be added in later releases. |

### `IdentitySubject`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `subjectRef` | Reference | `1` | Core | Primary reference to the identity subject. | Main identity anchor of the subject in the model. |
| `subjectCategory` | Code | `0..1` | Core | Category of the subject. | Examples: human, organization, device, service. |
| `homeContextRef` | Reference | `0..1` | Core | Primary or home identity context of the subject. | Examples: tenant, organization, federation realm. |
| `subjectStatus` | Code | `0..1` | Core | Current status of the subject. | Examples: active, disabled, revoked. |
| `profileRef` | Reference | `0..*` | Deferred | Reference to extended subject profiles. | Intended for later profile-based enrichment. |

### `IdentityProvider`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `providerId` | Identifier / URI | `1` | Core | Stable identifier of the identity provider. | Main identity anchor for the provider. |
| `providerType` | Code | `1` | Core | Type of provider. | Examples: enterprise IdP, issuer, federation provider. |
| `managedContextRef` | Reference | `0..*` | Core | Identity contexts managed by the provider. | Examples: tenant, domain, realm. |
| `trustReferenceRef` | Reference | `0..*` | Core | Reference to trust information related to the provider. | Supports trust alignment. |
| `serviceEndpointRef` | URI / Reference | `0..*` | Profile | Operational service endpoints of the provider. | Better kept in a profile layer. |

### `CredentialServiceProvider`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `cspId` | Identifier / URI | `1` | Core | Stable identifier of the credential service provider. | Identity anchor of the CSP. |
| `serviceType` | Code | `1` | Core | Type of credential-related service. | Examples: issuance, lifecycle management, administration. |
| `issuerAuthorityRef` | Reference | `0..1` | Core | Reference to the issuing authority. | Useful for issuer traceability. |
| `managedCredentialType` | Code / String | `0..*` | Core | Credential types managed by the CSP. | Supports type-level traceability. |
| `protocolRef` | Reference | `0..*` | Profile | Reference to the issuance or management protocol. | Better kept outside the core. |

### `RelyingParty`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `rpId` | Identifier | `1` | Core | Stable identifier of the relying party. | Main RP anchor. |
| `rpType` | Code | `1` | Core | Type of relying party. | Examples: application, service, portal, API. |
| `audienceRef` | Reference | `0..*` | Core | Reference to intended audience or service target. | Supports audience/resource alignment. |
| `requestedScopeRef` | Reference | `0..*` | Core | Requested scopes, permissions, or access targets. | Relevant to authorization reasoning. |
| `clientMetadataRef` | Reference | `0..1` | Profile | Reference to application/client metadata. | Better kept in profile documentation. |

### `Verifier`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `verifierId` | Identifier | `1` | Core | Stable identifier of the verifier. | Supports authentication traceability. |
| `verifierType` | Code | `1` | Core | Type of verifier. | Examples: human verifier, system verifier, automated verifier. |
| `verificationContextRef` | Reference | `0..1` | Core | Context in which verification occurs. | Useful for scenario scoping. |
| `verificationPolicyRef` | Reference | `0..*` | Profile | Verification policy references. | Better modeled outside the current core. |

### `Subscriber`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `subscriberId` | Identifier | `1` | Core | Identifier of the subscriber role instance. | Identifies a specific role occurrence. |
| `holderRef` | Reference | `1` | Core | Reference to the holder associated with the subscriber. | Connects the role to its holder/subject. |
| `subscriptionStatus` | Code | `0..1` | Core | Current status of the subscriber role. | Examples: active, pending, revoked. |
| `subscriptionType` | Code | `0..1` | Deferred | Type of subscription or membership. | Can be added later if needed. |

---

## 2. Identity Representation and Context

### `DigitalIdentity`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `digitalIdentityId` | Identifier | `1` | Core | Identifier of the digital identity representation. | Identifies the representation artifact itself. |
| `subjectRef` | Reference | `1` | Core | Reference to the represented identity subject. | Main subject linkage. |
| `contextRef` | Reference | `1` | Core | Reference to the identity context. | Defines the scope of interpretation. |
| `representationType` | Code | `0..1` | Core | Type of representation. | Examples: token-based, credential-based, account-based. |
| `lifecycleStatus` | Code | `0..1` | Core | Lifecycle status of the digital identity. | Examples: active, suspended, archived. |
| `trustReferenceRef` | Reference | `0..*` | Core | Reference to related trust hooks. | Supports trust alignment. |
| `representationFormat` | String | `0..1` | Profile | Concrete operational format of the representation. | Examples: JSON, JWT, VC, record format. |

### `IdentityContext`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `contextId` | Identifier | `1` | Core | Stable identifier of the identity context. | Main context anchor. |
| `contextType` | Code | `1` | Core | Type of context. | Examples: tenant, organization, realm, federation. |
| `domainRef` | Reference / String | `0..1` | Core | Organizational or technical domain reference. | Examples: domain, account, tenant. |
| `jurisdictionRef` | Reference / String | `0..1` | Core | Legal or governance jurisdiction reference. | Useful for cross-border or regulatory settings. |
| `policyRef` | Reference | `0..*` | Profile | References to policies that govern the context. | Better handled outside the minimal core. |

### `Identifier`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `identifierValue` | String | `1` | Core | Actual value of the identifier. | Raw identifier value. |
| `identifierScheme` | Code / String | `1` | Core | Scheme or namespace of the identifier. | Examples: DID, URI, UUID, GUID, ARN. |
| `identifierScopeRef` | Reference | `0..1` | Core | Scope in which the identifier is valid or meaningful. | Supports contextual interpretation. |
| `isPrimary` | Boolean | `0..1` | Core | Indicates whether this is the primary identifier. | Useful when multiple identifiers exist. |
| `normalizationRule` | String | `0..1` | Deferred | Rule or method for identifier normalization. | Can be added later. |

### `TrustReference`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `trustReferenceId` | Identifier | `1` | Core | Stable identifier of the trust reference. | Main trust hook identifier. |
| `trustSource` | String / Reference | `0..1` | Core | Source of the trust information. | Framework, authority, policy source, or external ontology source. |
| `trustFrameworkName` | String | `0..1` | Core | Name of the trust framework. | Supports external framework naming and documentation. |
| `alignmentTargetRef` | Reference | `0..*` | Core | References to external trust concepts or alignment targets. | Enables modular trust alignment. |
| `contextRef` | Reference | `1` | Core | Context in which the trust reference is interpreted. | Maintains scoping. |
| `evidenceReference` | Reference | `0..*` | Profile | Trust evidence or attestation references. | Better kept outside the current core. |
| `trustScore` | Number | `0..1` | Deferred | Quantitative trust score. | Not necessary in the current core. |

### `ONTrust:Trust`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `externalConceptRef` | URI / Identifier | `1` | Core | Reference to the external trust concept. | Sufficient for external alignment. |
| `externalLabel` | String | `0..1` | Core | Human-readable label of the external concept. | Useful for display and documentation. |
| `externalVersionRef` | URI / String | `0..1` | Deferred | Version reference of the external source. | May be added in later versions. |

---

## 3. Attributes, Claims, and Credentials

### `IdentityAttribute`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `attributeId` | Identifier | `1` | Core | Stable identifier of the attribute. | Main attribute anchor. |
| `attributeType` | Code / String | `1` | Core | Type of the attribute. | Examples: name, role, age, affiliation, assurance. |
| `valueType` | Code | `1` | Core | Type of the attribute value. | Examples: string, number, boolean, date, structured. |
| `attributeValue` | Literal / Structured Value | `1` | Core | Value of the attribute. | Core informational content of the attribute. |
| `attributeSourceRef` | Reference | `0..1` | Core | Source of the attribute. | Source system or authority. |
| `confidenceLevel` | Code / Number | `0..1` | Profile | Confidence or quality indicator of the attribute. | Better handled in profile layers. |

### `Claim`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `claimId` | Identifier | `1` | Core | Stable identifier of the claim. | Main claim anchor. |
| `claimType` | Code / String | `1` | Core | Semantic type of the claim. | Examples: identity claim, entitlement claim, status claim. |
| `aboutSubjectRef` | Reference | `1` | Core | Reference to the subject the claim is about. | Subject anchoring of the claim. |
| `assertedAttributeRef` | Reference | `1..*` | Core | References to asserted attributes. | Connects the claim to one or more asserted attributes. |
| `claimValue` | Literal / Structured Value | `0..1` | Core | Value asserted by the claim. | Used when the claim carries direct payload. |
| `claimIssuerRef` | Reference | `0..1` | Core | Reference to the issuer or source of the claim. | Supports provenance. |
| `claimIssuedAt` | DateTime | `0..1` | Core | Issuance or assertion time of the claim. | Supports traceability. |
| `claimEvidenceRef` | Reference | `0..*` | Profile | References to supporting evidence or proof. | Better left outside the minimal core. |
| `claimStatus` | Code | `0..1` | Deferred | Status of the claim. | Can be introduced later. |

### `Credential`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `credentialId` | Identifier / URI | `1` | Core | Stable identifier of the credential. | Main credential anchor. |
| `credentialType` | Code / String | `1..*` | Core | Type or category of the credential. | Supports typing and classification. |
| `issuerRef` | Reference | `1` | Core | Reference to the issuer of the credential. | Main provenance anchor. |
| `holderRef` | Reference | `0..1` | Core | Reference to the holder of the credential. | Holder linkage where applicable. |
| `subjectRef` | Reference | `0..*` | Core | References to subjects covered by the credential. | Useful for multi-subject or subject-bound credentials. |
| `issuanceTime` | DateTime | `0..1` | Core | Time of issuance. | Basic temporal traceability. |
| `validFrom` | DateTime | `0..1` | Core | Lower bound of validity. | Validity start. |
| `validUntil` | DateTime | `0..1` | Core | Upper bound of validity. | Validity end. |
| `statusReference` | Reference | `0..*` | Core | References to status or revocation information. | Supports lifecycle reasoning. |
| `boundAuthenticatorRef` | Reference | `0..1` | Core | Reference to authenticator bound to the credential. | Useful for binding semantics. |
| `supportedClaimRef` | Reference | `1..*` | Core | References to supported claims. | Represents the conceptual content carried or supported by the credential. |
| `proofRef` | Reference | `0..*` | Profile | References to proof or signature materials. | Better kept in profile layers. |
| `schemaRef` | Reference | `0..1` | Profile | Reference to schema or data model. | Better kept outside the core. |

---

## 4. Authentication, Authorization, and Outcomes

### `Authentication`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `authenticationId` | Identifier | `1` | Core | Stable identifier of the authentication event. | Main event anchor. |
| `authenticationTime` | DateTime | `1` | Core | Time of authentication. | Mandatory core traceability field. |
| `subjectParticipantRef` | Reference | `1` | Core | Reference to the participating subject. | Subject involved in the event. |
| `verifierRef` | Reference | `0..1` | Core | Reference to the verifier. | Verifier participation. |
| `authenticatorRef` | Reference | `0..*` | Core | References to authenticators used in the event. | Supports factor and authenticator modeling. |
| `claimRef` | Reference | `0..*` | Core | References to participating claims. | Included because claims explicitly participate in the current diagram. |
| `contextRef` | Reference | `0..1` | Core | Context in which the event takes place. | Supports contextual reasoning. |
| `resultRef` | Reference | `1` | Core | Reference to the event outcome. | Must link to `AuthenticationResult`. |
| `authenticationMethodRef` | Reference / Code | `0..*` | Profile | References to authentication methods. | Better handled in profile layers. |
| `authenticationContextRef` | Reference / Code | `0..1` | Profile | Authentication context class or assurance context. | Better handled in profile layers. |
| `nonceOrSessionBinding` | String | `0..1` | Profile | Session or anti-replay binding value. | Out of scope for the current minimal core. |

### `AuthenticationResult`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `resultId` | Identifier | `1` | Core | Stable identifier of the authentication result. | Main outcome anchor. |
| `decision` | Code | `1` | Core | Decision or outcome value. | Examples: success, failure, challenge, partial. |
| `assuranceLevel` | Code / String | `0..1` | Core | Level or strength of the authentication outcome. | Supports assurance interpretation without overfitting. |
| `reasonCode` | Code / String | `0..1` | Core | Reason or explanation code for the outcome. | Supports traceability and diagnostics. |
| `rawEvidenceRef` | Reference | `0..*` | Deferred | References to raw evidence underlying the result. | May be added later. |

### `Authorization`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `authorizationId` | Identifier | `1` | Core | Stable identifier of the authorization event. | Main event anchor. |
| `authorizationTime` | DateTime | `1` | Core | Time of authorization. | Mandatory temporal field. |
| `relyingPartyRef` | Reference | `1` | Core | Reference to the relying party involved in the decision. | Main participant anchor. |
| `evaluatedClaimRef` | Reference | `1..*` | Core | References to the claims evaluated in the decision. | Reflects current CM4DI structure. |
| `resourceRef` | Reference / Code | `0..*` | Core | Resource(s) targeted by the authorization event. | Supports access reasoning. |
| `actionRef` | Reference / Code | `0..*` | Core | Action(s) requested or evaluated. | Supports action-oriented authorization reasoning. |
| `contextRef` | Reference | `0..1` | Core | Context in which the authorization decision occurs. | Preserves contextual interpretation. |
| `resultRef` | Reference | `1` | Core | Reference to the authorization outcome. | Must link to `AuthorizationResult`. |
| `conditionRef` | Reference | `0..*` | Profile | References to evaluated conditions. | Better handled in a profile layer. |
| `policyRef` | Reference | `0..*` | Deferred | References to policies affecting the decision. | May be added in later versions. |

### `AuthorizationResult`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `resultId` | Identifier | `1` | Core | Stable identifier of the authorization result. | Main outcome anchor. |
| `decision` | Code | `1` | Core | Authorization decision value. | Examples: permit, deny, conditional. |
| `reasonCode` | Code / String | `0..1` | Core | Reason or explanation code for the decision. | Supports audit and diagnostics. |
| `grantedScopeOrAction` | Reference / Code | `0..*` | Core | Granted scopes, permissions, or actions. | Minimal but useful decision output. |
| `obligationRef` | Reference | `0..*` | Deferred | Obligations or advice attached to the decision. | May be added in future releases. |

---

## 5. Mediation, Binding, and Trust

### `Enrollment`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `enrollmentId` | Identifier | `1` | Core | Stable identifier of the enrollment relation instance. | Main relator anchor. |
| `subscriberRef` | Reference | `1` | Core | Reference to the subscriber involved in the enrollment. | Required participant. |
| `providerRef` | Reference | `1` | Core | Reference to the provider involved in the enrollment. | Required participant. |
| `enrollmentTime` | DateTime | `0..1` | Core | Time of enrollment. | Useful for timeline traceability. |
| `enrollmentStatus` | Code | `0..1` | Core | Current status of the enrollment. | Examples: active, pending, revoked. |
| `registrationChannel` | Code | `0..1` | Deferred | Channel through which the enrollment occurred. | Future enhancement. |

### `Authenticator`

| Canonical Field | Value Type | Cardinality | Status | Definition | Notes |
|---|---|---|---|---|---|
| `authenticatorId` | Identifier | `1` | Core | Stable identifier of the authenticator. | Main authenticator anchor. |
| `authenticatorType` | Code | `1` | Core | Type of authenticator. | Examples: password, OTP, key, device, certificate. |
| `bindingStatus` | Code | `0..1` | Core | Current binding status of the authenticator. | Examples: active, bound, revoked. |
| `assuranceHint` | Code / String | `0..1` | Core | Lightweight indication of assurance or strength. | Keeps the core useful without overengineering. |
| `cryptoMaterialRef` | Reference | `0..*` | Profile | References to cryptographic material. | Better kept outside the current core. |

---

## Fields Intentionally Excluded from the Current Core

The following field families are intentionally excluded from CM4DI core v0.1 and should remain in profile layers or later extensions.

### OIDC-Oriented Fields
- `nonce`
- `acr`
- `amr`
- `azp`
- `at_hash`
- `c_hash`
- token header fields
- JOSE/JWT serialization details

### VC-Oriented Fields
- `proof`
- `credentialSchema`
- `termsOfUse`
- presentation-specific fields
- advanced `credentialStatus` substructures

### Amazon IAM-Oriented Fields
- full JSON policy statement structure
- service-specific condition keys
- ARN decomposition details
- low-level policy serialization details

### Microsoft Identity Platform-Oriented Fields
- vendor-specific optional claims
- `groups`
- `roles`
- token-family internal claims
- application-specific optional claims as core properties

---

## Why This Registry Is the Best Choice for the Current Version

This registry is the best choice for the current CM4DI version because it preserves three critical balances.

### 1. Balance between sufficiency and overengineering
The selected fields are enough to make each class operationally meaningful inside a core ontology, but not so many that CM4DI collapses into a vendor-specific schema or protocol-level data model.

### 2. Balance between ontology semantics and implementation syntax
The fields are ontology-level and conceptually stable: identifiers, subject linkage, issuer/holder linkage, context, validity, participation, and result. Syntax-level elements are intentionally left to profile layers.

### 3. Balance between present usability and future extensibility
The current field set is sufficient for:
- ontology documentation
- ontology population
- scenario instantiation
- cross-standard mapping
- future OWL enrichment

At the same time, it leaves room for:
- OIDC profile mappings
- VC profile mappings
- IAM profile mappings
- Microsoft identity profile mappings
- governance, consent, assurance, and lifecycle extensions

---

## Suggested Next Artifacts

The following companion files are recommended for the next iteration:

- `CM4DI-OIDC-profile.md`
- `CM4DI-VC-profile.md`
- `CM4DI-IAM-profile.md`
- `CM4DI-Microsoft-profile.md`
- `CM4DI-field-to-owl-mapping.md`

---

## Version

**CM4DI Field Registry v0.1**
