# CM4DI Journal V2 — Domain Boundaries and Ubiquitous Language

## Purpose
This file fixes the semantic language used during Wave 5 so that evidence, model, profiles, mappings, CQs and later OWL formalization use the same terms. English labels are canonical; Persian labels are explanatory only.

## Bounded semantic domains

| Domain | Canonical purpose | Core status | Main profile destination |
|---|---|---|---|
| Identity Subjecthood | What entity is represented/identified in a given identity-management situation | Core pattern | P03 adds workload/device/agent kinds |
| Digital Representation | DigitalIdentity, Identifier and IdentityContext | Core | Account/Profile/AdministrativeDomain in P01 |
| Identity Information | IdentityAttribute, Claim, Evidence, provenance and binding | Core | Attribute mapping/source systems in P01; attestations in P04 |
| Credential Semantics | Credential, issuance, status and lifecycle | Core minimum | Wallet/presentation/controller in P02; device/SVID in P03 |
| Proofing & Enrollment | Establishment of confidence and binding before/while creating managed representation | Core | Government/legal proofing in P04 |
| Authentication | Verification event, authenticator and result | Core | Session/social login/federation mechanics in P01 |
| Authorization | Principal, Resource, Action, Request, Context, Permission, Grant, Decision and Delegation | Core minimum | Detailed policies/role bundles in P01 |
| Trust & Assurance | Trust hook and multidimensional AssuranceAssessment | Core hook | Frameworks, registries, anchors and conformance in P04 |
| Federation & Provisioning | Cross-domain authentication/brokering and account synchronization | Profile | P01 |
| Wallet / VC | Issuer, Holder, Presentation, Wallet, Controller and selective disclosure | Profile | P02 |
| Machine Identity | Workload, Device, Service Account, Attestation and AI Agent identity | Profile using Core patterns | P03 |
| Government / Institutional Trust | LegalIdentity, PID, governance authorities, certification/accreditation | Profile | P04 |
| Social Identity | Group/role selfhood, persona, reputation, salience | Out of CM4DI | Future independent ontology |

## Canonical bilingual vocabulary

| English canonical term | Persian explanatory term | Definition / usage constraint |
|---|---|---|
| IdentitySubject | موضوع هویت | Contextual role of an entity that identity information or a digital identity is about. It is not restricted to humans. |
| Party | طرف/بازیگر تعامل | Contextual participant in an identity-related interaction. Do not use as a universal superclass of all identity-bearing things. |
| DigitalIdentity | هویت دیجیتال / بازنمایی هویتی دیجیتال | A managed digital representation of an IdentitySubject in an IdentityContext. Not the real-world subject itself. |
| Identifier | شناسه | Information/sign used to distinguish or reference an entity/representation within a scheme/scope. DID and SPIFFE ID are profile mappings. |
| IdentityContext | زمینه هویتی | Context in which a DigitalIdentity/Identifier/identity information is interpreted. Not Tenant, TrustDomain, Audience or social context by default. |
| IdentityAttribute | ویژگی هویتی | Information element representing a property/value about a subject; do not assume it is an intrinsic ontological quality. |
| Claim | ادعا/گزاره درباره هویت | Assertion with proposition-level meaning about a subject; protocol token members are mappings, not the definition. |
| Evidence | شاهد/مدرک | Information artifact used to support a claim, proofing, binding, attestation or assessment. |
| Proof | اثبات/مدرک اثباتی | Role/use of evidence that supports verification of a proposition or binding; cryptographic proof mechanisms stay profile-specific. |
| Credential | اعتبارنامه | Issued information artifact carrying/supporting claims and provenance; may be human or non-human. |
| IdentityProofing | احراز/اثبات اولیه هویت | Process/event that establishes confidence in claimed real-world/subject identity. Not Authentication. |
| Enrollment | ثبت‌نام هویتی | Process/event that establishes a managed identity relationship/representation in a system/context. Not Provisioning. |
| IdentityBinding | پیوند هویتی | Relational pattern linking subject, representation/credential/authenticator and supporting evidence. |
| Authentication | اصالت‌سنجی | Event/process verifying an entity/claimant or control of an authenticator in context. Not proofing or authorization. |
| Authenticator | ابزار/عامل اصالت‌سنجی | Contextual role played by a device, secret, key or other bearer used in Authentication. |
| AuthenticationResult | نتیجه اصالت‌سنجی | Information record/result of an Authentication; distinct from Session. |
| Principal | اصل/فاعل مجازشناسی | Contextual authorization role that may be played by a person, account, group, workload or other representation. |
| Resource | منبع حفاظت‌شده | Contextual role of an entity or information resource targeted by authorization. |
| Action | عمل مورد درخواست | Action type/intention evaluated for access to a Resource. |
| AuthorizationRequest | درخواست مجوز | Information object specifying principal, resource, action and authorization context. |
| AuthorizationContext | زمینه مجوزدهی | Environmental/request context for an authorization evaluation; distinct from IdentityContext. |
| Permission | اجازه | Normative authorization unit describing an allowed action/resource scope. |
| AccessGrant | اعطای دسترسی | Relator/assignment connecting a Principal with Permission and scope/resource for a validity/context. Not an Authorization decision event. |
| Delegation | تفویض | Relator that authorizes one actor/principal to act on behalf of another within a scope. |
| AuthorizationResult | نتیجه/تصمیم مجوزدهی | Explicit decision record (e.g., permit/deny) produced by Authorization. |
| AssuranceAssessment | ارزیابی سطح اطمینان | Assessment with explicit dimension (proofing, authentication, attribute, federation, etc.) and level/value. |
| TrustAssessment | ارزیابی اعتماد | Assessment/hook for trust semantics; distinct from institutional certification and cryptographic validation. |
| RelyingParty | طرف اتکاکننده | Anti-rigid interaction role played by an organization/software/service that relies on identity/authentication information. |
| Verifier | راستی‌آزما | Generic verification role pattern; concrete AuthenticationVerifier and CredentialPresentationVerifier semantics must be explicit. |
| Account | حساب هویتی | Platform-local managed identity representation in P01; not the subject and not automatically identical to DigitalIdentity in every paradigm. |
| Session | نشست امنیتی | Temporally extended operational security context in P01; not AuthenticationResult. |
| Federation | فدراسیون هویتی | Profile-level arrangement connecting identity domains/providers/relying parties through trust and protocol/configuration. |
| Workload | بارکاری اجرایی | Running software/process/container/job capable of playing IdentitySubject/Principal roles in P03. |
| Device | دستگاه | Physical/virtual device that can play IdentitySubject; distinct from DeviceIdentityRecord, credential and Authenticator role. |
| AI Agent | عامل هوش مصنوعی | Agentive software specialization in P03; profile-first due domain immaturity. |
| SocialIdentity | هویت اجتماعی | Psychosocial/group-based self-concept. Explicitly outside CM4DI Core and profiles except bridge mappings. |

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