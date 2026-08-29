# CM4DI Core Concept Reference v2

Status: **governed Gate-C semantics with source-citation hardening in progress**.  
This document is a human-readable companion to `model/journal-v2/CM4DI_CORE_CONCEPT_REGISTRY_v2.csv`. Definitions are CM4DI semantic definitions; external sources support, constrain or contextualize them but do not replace the ontology definition.

## Reference principles

- A standard or vendor term is not automatically equivalent to a CM4DI concept.
- ISO, NIST, W3C, OpenID, IETF and official institutional sources are preferred for normative support.
- Operational IAM sources are used as implementation evidence and mapping targets.
- UFO/OntoUML category commitments remain governed by the Gate-C registry and the forthcoming formal-projection work in Issue #69.
- `Domain != Bounded Context != Profile != OWL Module`.

## Identity Semantics Context

| ID | English | فارسی | Canonical CM4DI definition | Primary supporting references |
|---|---|---|---|---|
| CM4DI-C0001 | Party | طرف مشارکت‌کننده | Contextual role played by an entity participating in an identity-related interaction; not a universal superclass of persons, organizations, devices or software. | [ISO/IEC 24760-1:2025](https://www.iso.org/standard/24760-1); [ISO/IEC 24760-2:2025](https://www.iso.org/standard/24760-2) |
| CM4DI-C0002 | IdentitySubject | موضوع هویت | Contextual role played by an entity that a DigitalIdentity, Claim, Credential or identity-management process is about. | [ISO/IEC 24760-1:2025](https://www.iso.org/standard/24760-1); [W3C DID Core](https://www.w3.org/TR/did-core/); [W3C VC Data Model 2.0](https://www.w3.org/TR/vc-data-model-2.0/) |
| CM4DI-C0003 | DigitalIdentity | هویت دیجیتال | Managed digital information/representation artifact that represents an IdentitySubject in an IdentityContext. It is not the represented entity itself. | [ISO/IEC 24760-1:2025](https://www.iso.org/standard/24760-1); [ISO/IEC 24760-2:2025](https://www.iso.org/standard/24760-2); [NIST SP 800-63-4](https://csrc.nist.gov/pubs/sp/800/63/4/final) |
| CM4DI-C0004 | Identifier | شناسه | Information/sign used to distinguish or reference an entity or representation under an identifier scheme and scope. | [ISO/IEC 24760-1:2025](https://www.iso.org/standard/24760-1); [W3C DID Core](https://www.w3.org/TR/did-core/); [SPIFFE Concepts](https://spiffe.io/docs/latest/spiffe-about/spiffe-concepts/) |
| CM4DI-C0005 | IdentityContext | زمینه هویتی | Contextual situation in which a DigitalIdentity, Identifier or identity information receives its intended identity-management interpretation. | [ISO/IEC 24760-2:2025](https://www.iso.org/standard/24760-2); [NIST SP 800-63-4](https://csrc.nist.gov/pubs/sp/800/63/4/final) |
| CM4DI-C0006 | IdentityAttribute | ویژگی هویتی | Information element representing a property/value attributed to an IdentitySubject for identity-management purposes. | [ISO/IEC 24760-1:2025](https://www.iso.org/standard/24760-1); [NIST SP 800-63A-4](https://csrc.nist.gov/pubs/sp/800/63/A/4/final); [W3C VC Data Model 2.0](https://www.w3.org/TR/vc-data-model-2.0/) |
| CM4DI-C0007 | Claim | ادعا | Assertion information object expressing a proposition about an IdentitySubject and optionally one or more IdentityAttributes. | [OpenID Connect Core 1.0](https://openid.net/specs/openid-connect-core-1_0.html); [W3C VC Data Model 2.0](https://www.w3.org/TR/vc-data-model-2.0/); [NIST SP 800-63C-4](https://csrc.nist.gov/pubs/sp/800/63/C/4/final) |

## Identity Assurance Context

| ID | English | فارسی | Canonical CM4DI definition | Primary supporting references |
|---|---|---|---|---|
| CM4DI-C0008 | Evidence | شواهد | Contextual evidence role played by an information artifact used to support a Claim, IdentityProofing, IdentityBinding, attestation or assessment. | [NIST SP 800-63A-4](https://csrc.nist.gov/pubs/sp/800/63/A/4/final); [W3C VC Data Model 2.0](https://www.w3.org/TR/vc-data-model-2.0/) |
| CM4DI-C0009 | Proof | اثبات | Specialized contextual Evidence role played when an artifact is used to establish or verify a proposition, binding or integrity claim. | [W3C VC Data Integrity 1.0](https://www.w3.org/TR/vc-data-integrity/); [WebAuthn Level 2](https://www.w3.org/TR/webauthn-2/) |
| CM4DI-C0010 | IdentityBinding | پیوند هویتی | Relator that mediates an IdentitySubject and one or more identity representations, credentials or authenticators and is grounded by evidence/provenance. | [NIST SP 800-63A-4](https://csrc.nist.gov/pubs/sp/800/63/A/4/final); [NIST SP 800-63B-4](https://csrc.nist.gov/pubs/sp/800/63/B/4/final); [WebAuthn Level 2](https://www.w3.org/TR/webauthn-2/) |
| CM4DI-C0015 | IdentityProofing | اعتبارسنجی اولیه هویت | Event/process that evaluates identity evidence to establish confidence that identity information refers or binds to the intended subject. It is not Authentication. | [NIST SP 800-63A-4](https://csrc.nist.gov/pubs/sp/800/63/A/4/final); [NIST SP 800-63-4](https://csrc.nist.gov/pubs/sp/800/63/4/final) |
| CM4DI-C0016 | Enrollment | ثبت هویتی | Event/process establishing a managed identity relationship or representation for an IdentitySubject within an identity-management context. It is distinct from Provisioning. | [NIST SP 800-63A-4](https://csrc.nist.gov/pubs/sp/800/63/A/4/final); [ISO/IEC 24760-2:2025](https://www.iso.org/standard/24760-2) |
| CM4DI-C0020 | AssuranceAssessment | ارزیابی اطمینان | Assessment artifact stating an assurance dimension, target and level/value/confidence with provenance/evidence. | [NIST SP 800-63-4](https://csrc.nist.gov/pubs/sp/800/63/4/final); [ISO/IEC 29115:2013](https://www.iso.org/standard/45138.html) |
| CM4DI-C0034 | Verifier | اعتبارسنج | Generic contextual role played by an entity that verifies evidence, authentication material or credential presentations; concrete verifier semantics are specialized by context. | [W3C VC Data Model 2.0](https://www.w3.org/TR/vc-data-model-2.0/); [NIST SP 800-63B-4](https://csrc.nist.gov/pubs/sp/800/63/B/4/final) |

## Credential Lifecycle Context

| ID | English | فارسی | Canonical CM4DI definition | Primary supporting references |
|---|---|---|---|---|
| CM4DI-C0011 | Credential | اعتبارنامه | Issued information artifact carrying/supporting Claims about one or more subjects with provenance and lifecycle/status semantics. | [W3C VC Data Model 2.0](https://www.w3.org/TR/vc-data-model-2.0/); [OpenID4VCI 1.0](https://openid.net/specs/openid-4-verifiable-credential-issuance-1_0-final.html); [NIST SP 800-63-4](https://csrc.nist.gov/pubs/sp/800/63/4/final) |
| CM4DI-C0012 | CredentialStatus | وضعیت اعتبارنامه | Dependent status mode of a Credential such as active, suspended, revoked, expired or otherwise invalid according to a status scheme. | [W3C Bitstring Status List v1.0](https://www.w3.org/TR/vc-bitstring-status-list/); [W3C VC Data Model 2.0](https://www.w3.org/TR/vc-data-model-2.0/) |
| CM4DI-C0013 | CredentialLifecycleEvent | رویداد چرخه حیات اعتبارنامه | Event that changes or establishes a lifecycle state/status of a Credential. | [W3C VC Data Model 2.0](https://www.w3.org/TR/vc-data-model-2.0/); [OpenID4VCI 1.0](https://openid.net/specs/openid-4-verifiable-credential-issuance-1_0-final.html) |
| CM4DI-C0014 | CredentialIssuance | صدور اعتبارنامه | Credential lifecycle event in which an issuer brings an issued Credential into existence or managed validity for a subject/holder context. | [OpenID4VCI 1.0](https://openid.net/specs/openid-4-verifiable-credential-issuance-1_0-final.html); [W3C VC Data Model 2.0](https://www.w3.org/TR/vc-data-model-2.0/) |

## Authentication Context

| ID | English | فارسی | Canonical CM4DI definition | Primary supporting references |
|---|---|---|---|---|
| CM4DI-C0017 | Authentication | احراز اصالت | Event/process that verifies an entity/claimant or control of an Authenticator under an authentication context and produces an AuthenticationResult. | [NIST SP 800-63B-4](https://csrc.nist.gov/pubs/sp/800/63/B/4/final); [WebAuthn Level 2](https://www.w3.org/TR/webauthn-2/) |
| CM4DI-C0018 | Authenticator | ابزار احراز اصالت | Contextual role played by a heterogeneous entity/artifact used during Authentication to demonstrate control, presence, knowledge or other authentication capability. | [NIST SP 800-63B-4](https://csrc.nist.gov/pubs/sp/800/63/B/4/final); [WebAuthn Level 2](https://www.w3.org/TR/webauthn-2/); [FIDO Alliance Specifications](https://fidoalliance.org/specifications/) |
| CM4DI-C0019 | AuthenticationResult | نتیجه احراز اصالت | Information/result artifact recording the outcome of an Authentication, including success/failure and references to assurance/context as needed. | [NIST SP 800-63B-4](https://csrc.nist.gov/pubs/sp/800/63/B/4/final); [LANL authentication dataset](https://csr.lanl.gov/data/auth/) |

## Authorization Context

| ID | English | فارسی | Canonical CM4DI definition | Primary supporting references |
|---|---|---|---|---|
| CM4DI-C0021 | Authorization | مجوزدهی | Event/process evaluating an AuthorizationRequest and producing an AuthorizationResult/decision. | [ISO/IEC 29146:2024](https://www.iso.org/standard/86013.html); [OpenID AuthZEN Authorization API 1.0](https://openid.net/specs/authorization-api-1_0.html); [XACML 3.0](https://docs.oasis-open.org/xacml/3.0/xacml-3.0-core-spec-os-en.html) |
| CM4DI-C0022 | AuthorizationRequest | درخواست مجوزدهی | Information object describing a requested Principal-Action-Resource access operation and associated AuthorizationContext. | [OpenID AuthZEN Authorization API 1.0](https://openid.net/specs/authorization-api-1_0.html); [XACML 3.0](https://docs.oasis-open.org/xacml/3.0/xacml-3.0-core-spec-os-en.html) |
| CM4DI-C0023 | AuthorizationContext | زمینه مجوزدهی | Situation/environmental context relevant to authorization evaluation such as time, device, network or request conditions. | [ISO/IEC 29146:2024](https://www.iso.org/standard/86013.html); [OpenID AuthZEN Authorization API 1.0](https://openid.net/specs/authorization-api-1_0.html) |
| CM4DI-C0024 | AuthorizationResult | نتیجه مجوزدهی | Decision/result artifact produced by Authorization recording an explicit authorization decision and references to request/context. | [OpenID AuthZEN Authorization API 1.0](https://openid.net/specs/authorization-api-1_0.html); [XACML 3.0](https://docs.oasis-open.org/xacml/3.0/xacml-3.0-core-spec-os-en.html) |
| CM4DI-C0025 | Principal | پرینسیپال / موجودیت اعمال دسترسی | Contextual role played by an entity or managed representation to which permissions/grants apply or that participates as authorization subject/actor. | [AWS IAM identities](https://docs.aws.amazon.com/IAM/latest/UserGuide/id.html); [Microsoft Entra application/service principals](https://learn.microsoft.com/en-us/entra/identity-platform/app-objects-and-service-principals); [Google Cloud IAM](https://cloud.google.com/iam/docs/overview) |
| CM4DI-C0026 | Resource | منبع | Contextual role played by an entity, information object or service that is the protected target of an authorization request or permission. | [ISO/IEC 29146:2024](https://www.iso.org/standard/86013.html); [OpenID AuthZEN Authorization API 1.0](https://openid.net/specs/authorization-api-1_0.html) |
| CM4DI-C0027 | Action | کنش | Description/specification of an action type or intended operation evaluated in authorization; not the executed event instance itself. | [OpenID AuthZEN Authorization API 1.0](https://openid.net/specs/authorization-api-1_0.html); [XACML 3.0](https://docs.oasis-open.org/xacml/3.0/xacml-3.0-core-spec-os-en.html) |
| CM4DI-C0028 | Permission | اجازه | Normative information object describing an allowed Action over a Resource or resource scope under defined semantics. | [AWS IAM policies and permissions](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html); [Google Cloud IAM](https://cloud.google.com/iam/docs/overview); [W3C ODRL 2.2](https://www.w3.org/TR/odrl-model/) |
| CM4DI-C0029 | AccessGrant | اعطای دسترسی | Relator/assignment that mediates a Principal with one or more Permissions and optional Resource/scope/validity, independently of runtime authorization decisions. | [AWS IAM Identity Center permission sets](https://docs.aws.amazon.com/singlesignon/latest/userguide/permissionsetsconcept.html); [Microsoft Entra groups/access](https://learn.microsoft.com/en-us/entra/fundamentals/concept-learn-about-groups); [ZITADEL role assignments](https://zitadel.com/docs/guides/manage/console/roles) |
| CM4DI-C0030 | Delegation | تفویض اختیار | Relator by which an authorizing party/principal empowers another actor/principal to exercise specified permissions or actions within a scope. | [RFC 8693 OAuth 2.0 Token Exchange](https://www.rfc-editor.org/rfc/rfc8693); [OpenID AuthZEN Authorization API 1.0](https://openid.net/specs/authorization-api-1_0.html) |

## Trust Governance Context

| ID | English | فارسی | Canonical CM4DI definition | Primary supporting references |
|---|---|---|---|---|
| CM4DI-C0031 | TrustAssessment | ارزیابی اعتماد | Assessment artifact concerning trust in a party, claim, credential, source or interaction, explicitly separated from governance-framework status and cryptographic validation. | [ONTrust repository](https://github.com/nemo-ufes/ONTrust); [EUDI Architecture and Reference Framework](https://github.com/eu-digital-identity-wallet/eudi-doc-architecture-and-reference-framework) |
| CM4DI-C0032 | TrustReference | مرجع اعتماد | Reference/alignment artifact that identifies an external trust concept, framework, source or alignment target relevant to CM4DI semantics. | [ONTrust repository](https://github.com/nemo-ufes/ONTrust); [OpenID Federation 1.1](https://openid.net/specs/openid-federation-1_1-final.html) |

## Federation Context

| ID | English | فارسی | Canonical CM4DI definition | Primary supporting references |
|---|---|---|---|---|
| CM4DI-C0033 | RelyingParty | طرف متکی | Contextual role played by an organization, software/service or other party that relies on identity, authentication or credential information in an interaction. | [NIST SP 800-63C-4](https://csrc.nist.gov/pubs/sp/800/63/C/4/final); [OpenID Connect Core](https://openid.net/specs/openid-connect-core-1_0.html); [WebAuthn Level 2](https://www.w3.org/TR/webauthn-2/) |

## Key anti-conflation rules

- `IdentitySubject != Account != UserProfile != DigitalIdentity`.
- `IdentityContext != Tenant != Realm != TrustDomain`.
- `IdentityProofing != Authentication`.
- `Enrollment != Provisioning`.
- `AuthenticationResult != Session`.
- `Principal != Person != IdentitySubject`.
- `AccessGrant != AuthorizationResult`.
- `Permission != IAM Role`; vendor roles normally map to `PermissionBundle` or assignment constructs.
- `Verifier` is generic; credential-presentation verification and authentication verification require contextual specialization.
- `TrustReference != TrustFramework != TrustRegistry != TrustAnchor`.

## Remaining work

Issue #77 extends this sourced reference to all 68 profile/extension concepts, adds bilingual Ubiquitous Language metadata, concept-to-evidence completeness metrics, neighbor-ontology decisions and exact CQ traceability. Formal OWL commitments remain downstream of Source Completeness and Issue #69.