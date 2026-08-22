# CM4DI Journal V2 — DDD Domain Boundaries and Ubiquitous Language

## Status
Current-facing canonical language after the 2026-08-22 DDD refactor (#50). The earlier Wave-5 table mixed semantic clusters, Profile views and technology groupings. Its underlying concept semantics remain valid, but its organizational taxonomy is superseded by the DDD registries under `model/journal-v2/ddd/`.

## Governing distinctions
- **Domain**: problem-space area of knowledge and activity.
- **Subdomain**: cohesive problem capability within the overall Digital Identity Management Domain.
- **Bounded Context**: explicit model/language ownership boundary in which terms have controlled meaning.
- **Profile**: cross-domain integration view for a standards/platform/ecosystem family.
- **Ontology Module**: formal packaging/import unit decided during Wave 7.

These are not synonyms and MUST NOT be used interchangeably.

## Naming rule
Canonical Domain and Bounded Context names MUST be coherent single phrases and MUST NOT contain `&`. Slash-composed multi-area labels are not canonical Domain names. Historical aliases may be retained only for lineage.

## Overall Domain
**Digital Identity Management** (`CM4DI-D0000`) covers the CM4DI problem space.

## Canonical DDD subdomains

| ID | Subdomain | Strategic type | Definition |
|---|---|---|---|
| CM4DI-D0001 | Identity Representation | Core | What entity is represented or identified and how a managed digital identity, identifier and context represent it. |
| CM4DI-D0002 | Identity Information | Core | Identity-related information and assertions about identity subjects. |
| CM4DI-D0003 | Identity Evidence | Core | Evidence, proof use, binding and assurance assessment supporting identity assertions and decisions. |
| CM4DI-D0004 | Identity Establishment | Core | Proofing and enrollment processes that establish confidence and managed identity relationships. |
| CM4DI-D0005 | Credential Management | Supporting | Protocol-neutral credential issuance, status and lifecycle. |
| CM4DI-D0006 | Authentication | Generic | Authentication events, authenticators, outcomes and security sessions. |
| CM4DI-D0007 | Authorization | Generic | Principals, resources, actions, requests, permissions, grants, delegation and decisions. |
| CM4DI-D0008 | Identity Administration | Supporting | Accounts, profiles, sources, stores, applications, provisioning and attribute mappings. |
| CM4DI-D0009 | Federation | Supporting | Cross-domain identity relationships, brokers, connections and relying interactions. |
| CM4DI-D0010 | Credential Exchange | Supporting | Holding, requesting, controlling, selectively disclosing and presenting credential-derived information. |
| CM4DI-D0011 | Workload Identity | Supporting | Runtime workload identity, service principals, attestation, trust domains and short-lived workload credentials. |
| CM4DI-D0012 | Device Identity | Supporting | Devices as identity-bearing entities and their managed identity records. |
| CM4DI-D0013 | Agent Identity | Supporting | Software-agent and AI-agent identity, agent representation and sponsor/accountability. |
| CM4DI-D0014 | Trust Governance | Core | Trust assessment/reference, governance frameworks, registries, anchors, conformance roles and participation status. |
| CM4DI-D0015 | Government Identity | Supporting | Legal identity, person-identification data, government attestations and governed identity providers. |

The authoritative scope, exclusions, lineage and neighboring-domain metadata are in `ddd/DOMAIN_REGISTRY_v2.csv`.

## Canonical Bounded Contexts

| ID | Bounded Context | Owned subdomains |
|---|---|---|
| CM4DI-BC0001 | Identity Semantics Context | Identity Representation; Identity Information |
| CM4DI-BC0002 | Identity Assurance Context | Identity Evidence; Identity Establishment |
| CM4DI-BC0003 | Credential Lifecycle Context | Credential Management |
| CM4DI-BC0004 | Authentication Context | Authentication |
| CM4DI-BC0005 | Authorization Context | Authorization |
| CM4DI-BC0006 | Identity Administration Context | Identity Administration |
| CM4DI-BC0007 | Federation Context | Federation |
| CM4DI-BC0008 | Credential Exchange Context | Credential Exchange |
| CM4DI-BC0009 | Workload Identity Context | Workload Identity |
| CM4DI-BC0010 | Device Identity Context | Device Identity |
| CM4DI-BC0011 | Agent Identity Context | Agent Identity |
| CM4DI-BC0012 | Trust Governance Context | Trust Governance |
| CM4DI-BC0013 | Government Identity Context | Government Identity |

The authoritative context ownership and dependencies are in `ddd/BOUNDED_CONTEXT_REGISTRY_v2.csv` and `ddd/CONTEXT_MAP_v2.md`.

## Profile rule
P01–P04 are cross-domain integration views, not Domains. Canonical profile display labels after the refactor are:
- P01 Enterprise Identity Profile
- P02 Verifiable Credential Profile
- P03 Technical Identity Profile
- P04 Governed Identity Profile

Historical profile labels remain aliases for lineage. See `ddd/DOMAIN_PROFILE_MATRIX_v2.csv`.

## Canonical bilingual vocabulary

| English canonical term | Persian explanatory term | Definition / usage constraint |
|---|---|---|
| IdentitySubject | موضوع هویت | Contextual role of an entity that identity information or a digital identity is about. It is not restricted to humans. |
| Party | طرف/بازیگر تعامل | Contextual participant in an identity-related interaction. Do not use as a universal superclass of all identity-bearing things. |
| DigitalIdentity | هویت دیجیتال / بازنمایی هویتی دیجیتال | Managed digital representation of an IdentitySubject in an IdentityContext. Not the real-world subject itself. |
| Identifier | شناسه | Information/sign used to distinguish or reference an entity/representation within a scheme/scope. DID and SPIFFE ID are mappings/specializations. |
| IdentityContext | زمینه هویتی | Context in which a DigitalIdentity/Identifier/identity information is interpreted. Not AdministrativeDomain, TrustDomain, Audience or social context by default. |
| IdentityAttribute | ویژگی هویتی | Information element representing a property/value about a subject; not automatically an intrinsic UFO quality. |
| Claim | ادعا/گزاره درباره هویت | Assertion with proposition-level meaning about a subject; protocol token members are mappings, not the definition. |
| Evidence | شاهد/مدرک | Contextual evidential role played by an artifact supporting a claim, proofing, binding, attestation or assessment. |
| Proof | اثبات/مدرک اثباتی | Specialized Evidence role when an artifact is used to establish or verify a proposition, binding or integrity claim. |
| Credential | اعتبارنامه | Issued information artifact carrying/supporting claims and provenance; may apply to human or non-human subjects. |
| IdentityProofing | احراز/اثبات اولیه هویت | Process establishing confidence in the claimed/intended identity subject. Not Authentication. |
| Enrollment | ثبت‌نام هویتی | Process establishing a managed identity relationship/representation. Not Provisioning. |
| IdentityBinding | پیوند هویتی | Relator linking subject, representation/credential/authenticator and supporting evidence. |
| Authentication | اصالت‌سنجی | Event/process verifying an actor or control of an authenticator in context. Not proofing or authorization. |
| Authenticator | ابزار/عامل اصالت‌سنجی | Contextual role played by a device, secret, key or other entity/artifact used in Authentication. |
| AuthenticationResult | نتیجه اصالت‌سنجی | Result artifact of Authentication; distinct from Session. |
| Session | نشست امنیتی | Temporally extended operational security context after/around authentication; not AuthenticationResult. |
| Principal | فاعل مجوزدهی | Contextual authorization role that may be played by a person, account, workload, device, agent or representation. |
| Resource | منبع حفاظت‌شده | Entity/information/service playing protected-target role in Authorization. |
| Action | عمل مورد درخواست | Action type or intended operation evaluated for access to a Resource. |
| AuthorizationRequest | درخواست مجوز | Information object specifying principal, resource, action and authorization context. |
| AuthorizationContext | زمینه مجوزدهی | Environmental/request context for authorization; distinct from IdentityContext. |
| Permission | اجازه | Normative authorization unit describing an allowed action/resource scope. |
| AccessGrant | اعطای دسترسی | Relator assigning Permission/scope to a Principal; not a runtime AuthorizationResult. |
| Delegation | تفویض | Relator empowering an actor/principal to act within a defined scope on behalf of another. |
| AuthorizationResult | نتیجه/تصمیم مجوزدهی | Explicit permit/deny or equivalent decision artifact produced by Authorization. |
| AssuranceAssessment | ارزیابی سطح اطمینان | Evidence-backed assessment with explicit assurance dimension and level/value/confidence. |
| TrustAssessment | ارزیابی اعتماد | Trust-oriented assessment distinct from governance certification and cryptographic validation. |
| RelyingParty | طرف اتکاکننده | Anti-rigid interaction role played by an organization/software/service relying on identity/authentication/credential information. |
| Verifier | راستی‌آزما | Generic verification role; concrete AuthenticationVerifier and CredentialPresentationVerifier semantics must remain explicit. |
| Account | حساب هویتی | Platform-local managed representation in Identity Administration; not the IdentitySubject. |
| Federation | فدراسیون هویتی | Cross-domain identity relationship managed in the Federation subdomain. |
| Workload | بارکاری اجرایی | Runtime software/process/container/job capable of IdentitySubject and Principal roles. |
| Device | دستگاه | Physical/virtual device distinct from its DeviceIdentityRecord, credentials and Authenticator role. |
| AIAgent | عامل هوش مصنوعی | AI-driven SoftwareAgent specialization in Agent Identity. |
| SocialIdentity | هویت اجتماعی | Psychosocial/group-based self-concept outside CM4DI except explicit bridge mappings. |

## Anti-conflation statements
1. IdentitySubject ≠ DigitalIdentity ≠ Account/Profile.
2. Identifier ≠ identity-bearing entity.
3. Claim ≠ IdentityAttribute ≠ Credential ≠ Evidence.
4. IdentityProofing ≠ Enrollment ≠ Provisioning ≠ Authentication.
5. AuthenticationResult ≠ Session.
6. Principal ≠ Person and IAM Role ≠ UFO Role.
7. AccessGrant ≠ AuthorizationResult.
8. IdentityContext ≠ AdministrativeDomain ≠ TrustDomain ≠ social context.
9. TrustAssessment ≠ TrustFramework ≠ Certification ≠ cryptographic validation.
10. Device ≠ Authenticator ≠ DeviceIdentityRecord ≠ DeviceCredential.
11. Workload ≠ ServiceAccount ≠ ServicePrincipal ≠ WorkloadIdentity.
12. SocialLogin ≠ SocialIdentity.
13. Domain ≠ BoundedContext ≠ Profile ≠ OntologyModule.

## Change-control note
This refactor changes organizational ownership and DDD language, not the stable identity criteria or OntoUML stereotypes of the Gate-C concepts. Any semantic change discovered during regression is handled separately through explicit change records and evaluation.