# Pharmaceutical Ecosystem Identity Case Study

## Overview

This document presents an OWL-aligned pharmaceutical ecosystem micro case study for evaluating **CM4DI** in a realistic but controlled domain setting. The case is intentionally small and traceable. Its purpose is to demonstrate that the core constructs of CM4DI can be instantiated coherently in a pharmaceutical ecosystem scenario involving a pharmacist, a professional credential, explicit claims about subject attributes, authentication, claim-based authorization, and modular trust alignment.

The pharmaceutical ecosystem context is provided by **CM-PharmE**, while **CM4DI remains the primary identity-centered ontological backbone**. CM-PharmE is therefore used only as the domain scaffold, not as the identity model under evaluation. This separation is consistent with the conceptual positioning of CM4DI as a minimal identity-centered backbone and with the pharmaceutical ecosystem framing of CM-PharmE. 

## Distinguishing CM4DI and CM-PharmE

### Role of CM4DI

CM4DI is the ontological artifact under evaluation. It structures:

- `IdentitySubject`
- contextual roles such as `Subscriber`, `IdentityProvider`, `Verifier`, and `RelyingParty`
- `DigitalIdentity`
- `IdentityContext`
- `Credential`
- `Claim`
- `IdentityAttribute`
- `Enrollment`
- `Authentication`
- `Authorization`
- `TrustReference`

The CM4DI paper explicitly states that credentials are held by a **Subscriber role assumed by an IdentitySubject**, that claims assert `IdentityAttribute` qualities about a subject, and that `Enrollment` grounds the subscriber–provider interaction. It also treats `DigitalIdentity` as an information object scoped by `IdentityContext`, and `Authentication` and `Authorization` as events. 

### Role of CM-PharmE

CM-PharmE provides the pharmaceutical ecosystem context for the scenario, including constructs such as healthcare provider, healthcare provider organization, and AI-enabled clinical decision support service. It is not the identity ontology being evaluated here. The case study simply instantiates CM4DI inside a pharmaceutical ecosystem context defined using CM-PharmE.

### Context References

- CM-PharmE IEEE page: <https://ieeexplore.ieee.org/abstract/document/11301544>
- CM-PharmE GitHub: <https://github.com/ArazSaieArasi3/CM-PharmE>

## Official Sources Used for Realistic Data Design

This case uses a curated micro-dataset inspired by official sources and standards.

- W3C Verifiable Credentials Data Model 2.0  
  <https://www.w3.org/TR/vc-data-model-2.0/>

- OpenID Connect Core 1.0  
  <https://openid.net/specs/openid-connect-core-1_0.html>

- CMS NPPES / NPI Files  
  <https://download.cms.gov/nppes/NPI_Files.html>

- HL7 FHIR PractitionerRole  
  <https://fhir.hl7.org/fhir/practitionerrole.html>

These sources are used only as structural inspiration for realistic data design. The dataset below is curated and scenario-specific, not a direct production export.

## Scenario Title

**Licensed Pharmacist Access to an AI-Enabled Clinical Decision Support Service**

## Scenario Description

A licensed pharmacist working in a healthcare provider organization seeks access to a medication-related function in an AI-enabled clinical decision support portal within a pharmaceutical ecosystem.

In the case:

1. the pharmacist is modeled as an `IdentitySubject`
2. the pharmacist also assumes a contextual `Subscriber` role
3. a `DigitalIdentity` represents the subject in a pharmaceutical access context
4. a professional credential is issued by a credential service provider and held by the subscriber
5. the subject has explicit `IdentityAttribute` instances
6. explicit `Claim` instances assert those attributes
7. an `Enrollment` instance grounds the subscriber–provider relation
8. an `Authenticator` is bound to the credential
9. an `Authentication` event occurs
10. an `Authorization` event evaluates claims and produces an authorization result
11. a `TrustReference` provides lightweight assurance alignment within the same context

This structure is aligned with the current CM4DI ontology design, where identity roles are explicit, `Enrollment` is the main relator, `Claim` asserts `IdentityAttribute`, and authorization is claim-evaluation-oriented rather than merely document-oriented. 

## Scope and Assumptions

### Included

- one pharmacist
- one subscriber role
- one healthcare provider organization
- one identity context
- one digital identity
- one credential service provider
- one enrollment
- one credential
- one authenticator
- four identity attributes
- four claims
- one identity provider
- one verifier
- one relying party
- one authentication event
- one authorization event
- one trust reference

### Excluded

- patient identity
- consent workflows
- policy language
- multi-credential federation
- large-scale empirical validation
- production hospital integration

## Actors and Core Instances

### Identity and Role Layer

| Instance ID | Instance Name | Type |
|---|---|---|
| SUBJ-001 | DrFarahRahimi | IdentitySubject |
| SUBR-001 | FarahSubscriberRole | Subscriber |
| CTX-001 | PharmaceuticalEcosystemAccessContext | IdentityContext |
| DI-001 | FarahDigitalIdentity | DigitalIdentity |

### Provider and Access Layer

| Instance ID | Instance Name | Type |
|---|---|---|
| CSP-001 | NationalPharmaceuticalCredentialAuthority | CredentialServiceProvider |
| ENR-001 | FarahCredentialEnrollment | Enrollment |
| AUTHC-001 | PharmaCareMFAAuthenticator | Authenticator |
| IDP-001 | PharmaCareIdentityProvider | IdentityProvider |
| VER-001 | CredentialVerificationService | Verifier |
| RP-001 | AICDSSPortal | RelyingParty |

### Domain Context Layer

| Instance ID | Instance Name | Type / Context |
|---|---|---|
| ORG-001 | PharmaCareHospital | Healthcare Provider Organization (CM-PharmE context) |
| DOM-001 | PharmacistActor | Healthcare Provider / Pharmacist (CM-PharmE context) |

### Credential and Attribute Layer

| Instance ID | Instance Name | Type |
|---|---|---|
| CRED-001 | ProfessionalPharmacistCredential | Credential |
| ATTR-001 | LicenseStatusAttribute | IdentityAttribute |
| ATTR-002 | OrganizationAffiliationAttribute | IdentityAttribute |
| ATTR-003 | PractitionerStatusAttribute | IdentityAttribute |
| ATTR-004 | SpecialtyAttribute | IdentityAttribute |
| CLM-001 | LicensedPharmacistClaim | Claim |
| CLM-002 | AffiliationClaim | Claim |
| CLM-003 | ActivePractitionerClaim | Claim |
| CLM-004 | SpecialtyClaim | Claim |

### Event and Trust Layer

| Instance ID | Instance Name | Type |
|---|---|---|
| AUTH-001 | PharmacistAuthenticationEvent | Authentication |
| AUTHR-001 | SuccessfulAuthenticationResult | AuthenticationResult |
| AUTHZ-001 | PharmacistAuthorizationEvent | Authorization |
| AUTHZR-001 | PermittedAuthorizationResult | AuthorizationResult |
| TRUST-001 | ProfessionalRegistryTrustReference | TrustReference |

## Curated Micro-Dataset

### Table A. Subject, Role, and Context

| instance_id | display_name | class | key_properties |
|---|---|---|---|
| SUBJ-001 | Dr. Farah Rahimi | IdentitySubject | partyId=SUBJ-001; subjectCategory=HumanProfessional; subjectStatus=Active |
| SUBR-001 | Farah Subscriber Role | Subscriber | subscriberId=SUBR-001 |
| CTX-001 | Pharmaceutical Ecosystem Access Context | IdentityContext | contextId=CTX-001; contextType=ProfessionalPharmaAccess |
| DI-001 | Farah Digital Identity | DigitalIdentity | digitalIdentityId=DI-001; subjectRef=SUBJ-001; contextRef=CTX-001 |

### Table B. Enrollment, Credential, and Authenticator

| instance_id | display_name | class | key_properties |
|---|---|---|---|
| CSP-001 | National Pharmaceutical Credential Authority | CredentialServiceProvider | cspId=CSP-001 |
| ENR-001 | Farah Credential Enrollment | Enrollment | enrollmentId=ENR-001; subscriberRef=SUBR-001; providerRef=CSP-001; enrollmentStatus=Active |
| AUTHC-001 | PharmaCare MFA Authenticator | Authenticator | authenticatorId=AUTHC-001; authenticatorType=MFA Token |
| CRED-001 | Professional Pharmacist Credential | Credential | credentialId=CRED-001; credentialType=ProfessionalPharmacistCredential; issuedBy=CSP-001; heldBy=SUBR-001; boundTo=AUTHC-001; credentialStatus=Valid |

### Table C. Identity Attributes

| instance_id | display_name | class | key_properties |
|---|---|---|---|
| ATTR-001 | License Status | IdentityAttribute | attributeId=ATTR-001; attributeType=LicenseStatus; attributeValue=Licensed |
| ATTR-002 | Organization Affiliation | IdentityAttribute | attributeId=ATTR-002; attributeType=Affiliation; attributeValue=PharmaCare Hospital |
| ATTR-003 | Practitioner Status | IdentityAttribute | attributeId=ATTR-003; attributeType=PractitionerStatus; attributeValue=Active |
| ATTR-004 | Specialty | IdentityAttribute | attributeId=ATTR-004; attributeType=Specialty; attributeValue=Clinical Pharmacy |

### Table D. Claims

| instance_id | display_name | class | key_properties |
|---|---|---|---|
| CLM-001 | Licensed Pharmacist Claim | Claim | claimId=CLM-001; claimType=ProfessionalLicensure; aboutSubjectRef=SUBJ-001; assertedAttributeRef=ATTR-001 |
| CLM-002 | Affiliation Claim | Claim | claimId=CLM-002; claimType=OrganizationalAffiliation; aboutSubjectRef=SUBJ-001; assertedAttributeRef=ATTR-002 |
| CLM-003 | Active Practitioner Claim | Claim | claimId=CLM-003; claimType=PractitionerStatus; aboutSubjectRef=SUBJ-001; assertedAttributeRef=ATTR-003 |
| CLM-004 | Specialty Claim | Claim | claimId=CLM-004; claimType=ProfessionalSpecialty; aboutSubjectRef=SUBJ-001; assertedAttributeRef=ATTR-004 |

### Table E. Authentication, Authorization, and Trust

| instance_id | display_name | class | key_properties |
|---|---|---|---|
| IDP-001 | PharmaCare Identity Provider | IdentityProvider | providerId=IDP-001 |
| VER-001 | Credential Verification Service | Verifier | verifierId=VER-001 |
| RP-001 | AI-Enabled Clinical Decision Support Portal | RelyingParty | rpId=RP-001 |
| AUTH-001 | Pharmacist Authentication Event | Authentication | authenticationId=AUTH-001; subjectParticipantRef=SUBJ-001; authenticationTime=2026-04-16T09:30:00Z; resultRef=AUTHR-001 |
| AUTHR-001 | Successful Authentication Result | AuthenticationResult | resultId=AUTHR-001; decision=Success |
| AUTHZ-001 | Pharmacist Authorization Event | Authorization | authorizationId=AUTHZ-001; relyingPartyRef=RP-001; evaluatedClaimRef=CLM-001,CLM-002,CLM-003,CLM-004; authorizationTime=2026-04-16T09:31:00Z; resultRef=AUTHZR-001 |
| AUTHZR-001 | Permitted Authorization Result | AuthorizationResult | resultId=AUTHZR-001; decision=Permitted; grantedScopeOrAction=Medication Decision Support Access |
| TRUST-001 | Professional Registry Trust Reference | TrustReference | trustReferenceId=TRUST-001; trustFrameworkName=Professional Registry Assurance; contextRef=CTX-001; assuranceLevel=Moderate |

## Key OWL-Aligned Structural Assertions

The current case is aligned with the latest ontology in the following ways:

1. **DigitalIdentity** is explicitly tied to exactly one `IdentitySubject` and one `IdentityContext`.
2. **Subscriber** is represented explicitly rather than being collapsed into the subject.
3. **Credential** is held by the `Subscriber`, issued by a `CredentialServiceProvider`, and bound to an `Authenticator`.
4. **Enrollment** explicitly mediates the relation between `Subscriber` and `CredentialServiceProvider`.
5. **Claim** is modeled as an explicit object with `claimId`, `claimType`, `aboutSubjectRef`, and `assertedAttributeRef`.
6. **IdentityAttribute** instances are separated from claims and treated as the asserted subject qualities.
7. **Authorization** evaluates one or more claims rather than merely “checking a credential”.
8. **TrustReference** is explicitly scoped to the same `IdentityContext`.

This is consistent with the CM4DI paper’s explicit treatment of Subscriber, Enrollment, Claim-to-IdentityAttribute semantics, contextual scoping, and event-based identity interaction. 

## Scenario Walkthrough

### Step 1. Domain Actor and Identity Subject

Dr. Farah Rahimi is a pharmacist in the pharmaceutical ecosystem context. At the domain level, this aligns with the healthcare provider notion in CM-PharmE. At the identity level, she is represented by `SUBJ-001`, an `IdentitySubject`.

### Step 2. Contextual Role Assumption

The same person also assumes the contextual role `SUBR-001`, a `Subscriber`. This reflects the CM4DI principle that contextual participation roles should be separated from the intrinsic identity-bearing subject. 

### Step 3. Identity Context and Digital Identity

`CTX-001` defines the Pharmaceutical Ecosystem Access Context. `DI-001` represents the pharmacist under this specific context.

### Step 4. Enrollment

`ENR-001` grounds the relationship between `SUBR-001` and `CSP-001`. This explicitly models the subscriber–provider mediation required by the ontology.

### Step 5. Credential and Authenticator Binding

`CRED-001` is a professional pharmacist credential issued by `CSP-001`, held by `SUBR-001`, and bound to `AUTHC-001`, the authenticator.

### Step 6. Identity Attributes

The pharmacist has four explicit identity attributes:
- licensed status
- organizational affiliation
- active practitioner status
- clinical pharmacy specialty

### Step 7. Claim Assertion

Four explicit claim instances assert these four attributes about `SUBJ-001`. This reflects the CM4DI principle that claims are social objects asserting identity attributes about a subject. 

### Step 8. Authentication

`AUTH-001` records an authentication event in which the subject participates and which produces `AUTHR-001 = Success`.

### Step 9. Authorization

`AUTHZ-001` records an authorization event by the relying party `RP-001`. The event evaluates claims `CLM-001` through `CLM-004` and produces `AUTHZR-001 = Permitted`.

### Step 10. Trust Alignment

`TRUST-001` provides a modular trust reference aligned with the same identity context. This preserves the lightweight trust integration strategy of CM4DI. 

## Mapping to CM4DI

| Case Element | CM4DI Construct |
|---|---|
| SUBJ-001 | IdentitySubject |
| SUBR-001 | Subscriber |
| CTX-001 | IdentityContext |
| DI-001 | DigitalIdentity |
| CSP-001 | CredentialServiceProvider |
| ENR-001 | Enrollment |
| AUTHC-001 | Authenticator |
| CRED-001 | Credential |
| ATTR-001..ATTR-004 | IdentityAttribute |
| CLM-001..CLM-004 | Claim |
| IDP-001 | IdentityProvider |
| VER-001 | Verifier |
| RP-001 | RelyingParty |
| AUTH-001 | Authentication |
| AUTHR-001 | AuthenticationResult |
| AUTHZ-001 | Authorization |
| AUTHZR-001 | AuthorizationResult |
| TRUST-001 | TrustReference |

## Mapping to CM-PharmE Context

| Case Element | CM-PharmE Contextual Role |
|---|---|
| Dr. Farah Rahimi | Healthcare Provider |
| PharmaCare Hospital | Healthcare Provider Organization |
| AICDSSPortal | AI-Enabled Clinical Decision Support System |
| Pharmaceutical Ecosystem Access Context | Pharmaceutical digital/operational ecosystem context |

## Competency Question Validation

### CQ1. Which IdentitySubject participates in a given IdentityContext, and through which contextual roles?

`SUBJ-001` participates in `CTX-001` and assumes the contextual role `SUBR-001` as Subscriber. This directly reflects the role-based identity participation logic described in the CM4DI evaluation framework. :contentReference[oaicite:7]{index=7}

### CQ2. Which Credential instances are associated with a given DigitalIdentity, and which Claim objects assert specific IdentityAttribute qualities?

`DI-001` represents `SUBJ-001` in `CTX-001`. `CRED-001` is held by the corresponding subscriber role `SUBR-001`. Claims `CLM-001` to `CLM-004` assert attributes `ATTR-001` to `ATTR-004` about `SUBJ-001`. This aligns with the CM4DI treatment of Claim as a social object asserting `IdentityAttribute` qualities. 

### CQ3. Under which conditions does Authorization occur?

Authorization occurs when authentication has succeeded, the relevant professional credential is valid, and the relying party evaluates the required claims successfully in the same identity context.

### CQ4. Under which contextual constraints can authorization occur?

Authorization is scoped to `CTX-001`, the pharmaceutical ecosystem access context. Outside this context, the same digital identity and claims may not entail the same access outcome.

### CQ5. Under which contextual and credential conditions can access be granted?

Access is granted when the pharmacist’s credential is valid, bound to an authenticator, backed by enrollment with a credential provider, and supports evaluated claims showing professional licensure, affiliation, active status, and specialty.

### CQ6. How is trust integrated without embedding a full trust ontology?

Trust is referenced via `TRUST-001`, which is scoped to the same context and acts as a lightweight assurance alignment artifact rather than a deeply embedded trust relator. This matches the modular trust strategy of CM4DI. 

## Interpretation

This revised case study is stronger than the earlier version for five reasons.

### 1. It preserves role/subject separation

The pharmacist is no longer treated only as a single flattened user entity. The distinction between `IdentitySubject` and `Subscriber` is now explicit, which better respects the ontological separation between intrinsic identity and contextual role participation. 

### 2. It makes enrollment explicit

The subscriber–provider mediation is no longer implicit. `Enrollment` is now represented directly, which is consistent with the CM4DI design rationale that restricts relator usage to the enrollment interaction. 

### 3. It models claims properly

Claims are now explicit objects rather than mere text columns. Each claim is linked to a subject and to one or more asserted identity attributes. This makes the case substantially more faithful to the ontology. 

### 4. It accounts for authenticator binding

The credential is now explicitly bound to an authenticator, which better fits the current formalization.

### 5. It makes authorization claim-centric

Authorization is now described as evaluating claims supported by a credential, rather than as a simplistic direct credential check. This is both conceptually cleaner and more faithful to the current ontology structure.

## Limitations

This is still a micro case study.

- It is not a production deployment.
- It uses curated scenario data inspired by official sources.
- It does not model patients, consent, or detailed policy artifacts.
- It does not attempt quantitative system validation.
- It is meant for conceptual-operational evaluation of CM4DI in a pharmaceutical ecosystem context.
