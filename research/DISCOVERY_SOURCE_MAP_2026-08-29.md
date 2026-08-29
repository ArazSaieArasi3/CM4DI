# CM4DI Discovery Source Map — 2026-08-29

## Purpose
Provide one navigational map of the material and supporting source families being examined for the PUB-003 journal ontology. This map is not a Source Completeness PASS; exact source-by-source coverage is governed under `conceptualization/source-mining/` and Issues #60–#66/#71–#77.

## 1. International identity and access standards

### ISO/IEC
- ISO/IEC 24760-1:2025 — Identity management core concepts and terminology — https://www.iso.org/standard/24760-1
- ISO/IEC 24760-2:2025 — Reference architecture and requirements — https://www.iso.org/standard/24760-2
- ISO/IEC 24760-3:2025 — Practice — tracked through ISO.
- ISO/IEC 29115:2013 and successor activity — authentication assurance — https://www.iso.org/standard/45138.html
- ISO/IEC 29146:2024 — access management — https://www.iso.org/standard/86013.html
- ISO/IEC 23220 family — mobile eID generic architectures and lifecycle.
- ISO/IEC 18013-5 and successor activity — mobile driving licence/mobile document ecosystem.

### NIST
- SP 800-63-4 — https://csrc.nist.gov/pubs/sp/800/63/4/final
- SP 800-63A-4 Identity Proofing and Enrollment — https://csrc.nist.gov/pubs/sp/800/63/A/4/final
- SP 800-63B-4 Authentication and Authenticator Management — https://csrc.nist.gov/pubs/sp/800/63/B/4/final
- SP 800-63C-4 Federation and Assertions — https://csrc.nist.gov/pubs/sp/800/63/C/4/final

### W3C
- Verifiable Credentials Data Model 2.0 — https://www.w3.org/TR/vc-data-model-2.0/
- DID Core — https://www.w3.org/TR/did-core/
- VC Data Integrity — https://www.w3.org/TR/vc-data-integrity/
- Controlled Identifiers — https://www.w3.org/TR/cid-1.0/
- Bitstring Status List — https://www.w3.org/TR/vc-bitstring-status-list/
- WebAuthn — https://www.w3.org/TR/webauthn-2/
- Digital Credentials API — current standards-development status monitored.

### OpenID Foundation
- OpenID Connect Core — https://openid.net/specs/openid-connect-core-1_0.html
- OpenID4VP — https://openid.net/specs/openid-4-verifiable-presentations-1_0.html
- OpenID4VCI — https://openid.net/specs/openid-4-verifiable-credential-issuance-1_0-final.html
- HAIP — current final profile lineage.
- OpenID Federation 1.1 — https://openid.net/specs/openid-federation-1_1-final.html
- Authorization API 1.0 / AuthZEN — https://openid.net/specs/authorization-api-1_0.html
- Identity Assurance — current final/errata lineage.

### IETF
- SCIM Core Schema RFC 7643 — https://www.rfc-editor.org/rfc/rfc7643
- SCIM Protocol RFC 7644 — https://www.rfc-editor.org/rfc/rfc7644
- current SCIM event/security updates where material.
- OAuth security BCP/current RFCs.
- JWT RFC 7519.
- OAuth Token Exchange RFC 8693 — https://www.rfc-editor.org/rfc/rfc8693
- current browser-based OAuth guidance where material.

### OASIS and FIDO
- SAML 2.0.
- XACML 3.0 — https://docs.oasis-open.org/xacml/3.0/xacml-3.0-core-spec-os-en.html
- FIDO2 / CTAP current stable lineage — https://fidoalliance.org/specifications/

## 2. European Digital Identity and regulatory ecosystem

Material EU sources are reviewed individually, not as one generic “EUDI” row.

- Regulation (EU) 2024/1183 — European Digital Identity Framework — https://eur-lex.europa.eu/eli/reg/2024/1183/oj
- Commission Implementing Regulation (EU) 2024/2977 — PID/EAA — current consolidated lineage.
- 2024/2979 — wallet integrity/core functionality.
- 2024/2980 — ecosystem notifications.
- 2024/2981 — certification of wallet solutions.
- 2024/2982 — protocols/interfaces.
- 2025/848 — wallet relying-party registration.
- 2026/1730 and 2026/1731 — amendment/standards lineage.
- EUDI Wallet Architecture and Reference Framework v3 lineage — https://github.com/eu-digital-identity-wallet/eudi-doc-architecture-and-reference-framework
- EUDI technical specifications and reference implementations.
- Functional Conformance Assessment Framework where concept/evaluation-bearing.
- EU Trusted Lists — https://digital-strategy.ec.europa.eu/en/policies/eu-trusted-lists

Primary ontology concerns: Wallet/User/Provider roles, PID/EAA, relying-party registration/intended use, trusted lists, registrars, trust anchors, certification/conformity, issuance/presentation/status, protocols and legally governed participation.

## 3. Global trust and government identity frameworks

- UK Digital Verification Services Trust Framework 1.0.
- UK GPG45 identity-checking guidance.
- UK attribute creation/binding/sharing guidance.
- Pan-Canadian Trust Framework including Authentication, Credentials and Trust Registries — https://diacc.ca/trust-framework/
- Australia Digital ID Act/system, accreditation rules and governance — https://www.digitalidsystem.gov.au/
- MOSIP architecture and partner ecosystem — https://docs.mosip.io/1.2.0/overview/architecture
- World Bank ID4D Principles and Global Dataset — https://id4d.worldbank.org/

## 4. Direct ontology and closest academic competitors

Mandatory closest-work revalidation under Issue #64 includes:
- MFSSIA 2026 — DOI 10.1016/j.teler.2026.100322 — direct UFO-grounded competitor in SSI authentication.
- Layouni and Pollet 2009 — OWL federated identity ontology — DOI 10.1109/AINA.2009.124.
- Nahar 2021 IAM ontology/metamodel.
- Comb and Martin 2026 — broad digital identity ontological synthesis — DOI 10.3390/info17010085.
- Richter and Anke 2026 — SSI conceptual framework.
- Yildiz et al. 2023 — SSI interoperability reference model.
- Schardong and Custodio 2022 — SSI systematic review/taxonomy — DOI 10.3390/s22155641.
- Ferdous et al. 2019 — formal SSI model.
- current 2025–2026 systematic/meta-synthesis and formal-ontology work that affects novelty claims.

Comparison covers foundational ontology, formalism, human/non-human scope, trust, proofing, authentication, authorization, credential lifecycle, standards mapping, operational mapping, datasets, CQs, reasoning, evaluation and reproducibility.

## 5. Neighbor ontologies and semantic vocabularies

CM4DI intends to integrate identity semantics while delegating mature generic semantics where appropriate.

- UFO / gUFO — https://github.com/nemo-ufes/gufo
- ONTrust — https://github.com/nemo-ufes/ONTrust
- PROV-O — https://www.w3.org/TR/prov-o/
- W3C Organization Ontology — https://www.w3.org/TR/vocab-org/
- ODRL 2.2 — https://www.w3.org/TR/odrl-model/
- Data Privacy Vocabulary — https://www.w3.org/community/reports/dpvcg/CG-FINAL-dpv-20240801/
- W3C VC/RDF vocabularies and identifier vocabularies.
- SKOS/Dublin Core for terminology/metadata only when justified.
- security/IAM/access-control ontologies discovered through the competitor wave.

Each receives a `reuse / align / bridge / specialize / do-not-import` decision rather than automatic imports.

## 6. Cloud IAM, IAM, CIAM and SSO products

Issue #72 currently benchmarks:

### Amazon/AWS
- AWS IAM
- AWS IAM Identity Center
- Amazon Cognito
- AWS STS as credential/token-exchange infrastructure

### Microsoft
- Microsoft Entra ID
- Microsoft Entra External ID
- Managed Identities
- service principals/application registrations
- hybrid directory/device concepts where material

### Google
- Google Cloud IAM
- Workforce Identity Federation
- Workload Identity Federation
- Google Cloud Identity

### Independent IAM/CIAM/SSO
- Okta Identity Engine / Universal Directory
- Auth0
- PingOne / Ping Identity
- Keycloak
- ZITADEL
- Ory Kratos / Hydra
- authentik
- Dex

Benchmark dimensions include Account/Profile/Source/Store, Tenant/Realm/Org, Application/Client, Group/Role/Permission/Grant, federation/brokering/social login/account linking, provisioning/SCIM, session/MFA/passkeys, workload/service accounts, policies/conditions, APIs/protocols, lifecycle and governance.

## 7. Directories, identity stores and persistence

- LDAP v3 / directory information model.
- Active Directory Domain Services.
- Microsoft Entra directory.
- Okta Universal Directory.
- Keycloak local store and user federation.
- Auth0 user stores/connections.
- Google Cloud Identity directory.
- SCIM User/Group resource models.
- relational persistence patterns.
- document/graph/event-oriented persistence considered as implementation alternatives, not ontology sources.

## 8. GitHub repositories, reference implementations and conformance suites

Selected current baseline:
- https://github.com/w3c/vc-data-model-2.0-test-suite
- https://github.com/openid-certification/conformance-suite
- EUDI wallet reference repositories including https://github.com/eu-digital-identity-wallet/eudi-lib-ios-wallet-kit
- https://github.com/keycloak/keycloak
- https://github.com/zitadel/zitadel
- https://github.com/ory/kratos
- https://github.com/ory/hydra
- https://github.com/goauthentik/authentik
- https://github.com/dexidp/dex
- https://github.com/spiffe/spire
- https://github.com/mosip/mosip-ref-impl

License, maintenance, owner authority, state transitions, test data and exact benchmark role must be recorded before executable reuse.

## 9. Datasets and empirical evaluation evidence

Current v2 registry:
- LANL User-Computer Authentication Associations in Time — DOI 10.11578/1160076.
- Risk-Based Authentication dataset — DOI 10.5281/zenodo.6782156.
- World Bank ID4D Global Dataset 2025.
- Global Findex 2025 + ID4D module — DOI 10.48529/bk9n-8r43.
- LANL Comprehensive Multi-Source Cyber-Security Events — candidate bounded authentication/AD slice.
- Behavior-based User Authentication Dataset — excluded from primary due access/narrowness.
- Pre-AttentiveGaze — monitor for optional authenticator-modality diversity.

The empirical portfolio is documented in `evaluation/EMPIRICAL_EVALUATION_PORTFOLIO_v2.md`.

## 10. Adjacent Research ecosystem

- R-031 SemSocialIdentity: separate Social Identity ontology; bridge only, not CM4DI module.
- R-003 Commentium: discourse/comment semantics.
- R-004 Newsium: news/information semantics.

Bridge terms such as persona, affiliation, author/source identity and reputation must not cause scope merger.

## 11. Discovery exit logic

A source family is not “done” because it appears in this list. Source Completeness requires:
1. material-source classification;
2. exact version/status and canonical locator;
3. source coverage/extraction;
4. semantic disposition of raw concepts/relations;
5. synonym/collision normalization;
6. concept/domain/BC/CQ/module regression;
7. unresolved gaps explicitly recorded;
8. final #66 and #60 PASS.

Until then Draft PR #59 remains an engineering module candidate rather than a frozen formal ontology architecture.