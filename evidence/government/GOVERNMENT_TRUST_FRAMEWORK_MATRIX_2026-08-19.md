# CM4DI Journal V2 — Government Digital Identity and Trust-Framework Matrix

**Review date:** 2026-08-19  
**Scope:** Issue #4 / roadmap D08–D10  
**Method:** bounded review of authoritative legal, institutional, architecture and implementation sources. The purpose is semantic extraction for CM4DI, not legal-compliance advice or an exhaustive country ranking.

## 1. Comparative matrix

| Ecosystem / framework | Current status at review date | Core actor/service distinctions | Trust / assurance mechanism | Lifecycle / governance signals | CM4DI implication |
|---|---|---|---|---|---|
| **EU eIDAS 2 / EUDI Wallet** | Regulation (EU) 2024/1183 in force; EUDI ARF **v3.0.0** released 2026-07-23 | Wallet User, Wallet Provider, PID Provider, Attestation Provider, Relying Party, Registrar, National Accreditation Body, trust-service roles | Member-State recognition, certification, trusted lists, trust anchors, RP registration, access/registration certificates, qualified status | Wallet issuance/use/revocation, PID/attestation issuance and revocation, provider certification, RP registration | Strong evidence that `TrustReference` alone is insufficient; registry/status/governance must be representable. EUDI-specific wallet internals stay profile-level. |
| **UK DVS Trust Framework** | **1.0 final** published 2026-06-09 but not yet effective; gamma **0.4 remains certifiable** at review date | Identity Service Provider, Attribute Service Provider, Holder Service Provider, Orchestration Service Provider, Component Service Provider, Relying Party | Independent certification against provider roles, statutory DVS register, confidence levels, provenance/binding metadata | identity checking, attribute creation/binding/sharing, holder account recovery/suspension/revocation/closure, certification status | Strong evidence for neutral provider-role patterns, holder-service semantics, register membership/status and provenance/confidence. UK role names remain profile mappings unless cross-framework recurrence supports abstraction. |
| **Canada PCTF** | Living modular framework; Authentication V1.2 and Trust Registries V1.0 final; Credentials module V1.0 final | Subject, Authentication/Credential Service Providers, Issuer, Verifier, Wallet Provider, Trust Registry participant | Modular conformance, levels of assurance, certified trusted processes, trust registries, trustmarks | credential/authentication lifecycle; registry registration/certification/suspension/revocation; attribute binding/maintenance/revocation | Strongest evidence that a `TrustRegistry` is a governed information service distinct from a `TrustAnchor`; also supports `TrustedProcess`/conformance semantics as profile-level. |
| **Australia Digital ID** | Digital ID Act 2024 and supporting instruments in force since 2024-11-30 | Identity Service Provider, Attribute Service Provider, Identity Exchange Provider, Relying Party, Digital ID Regulator, System Administrator, Data Standards Chair | Voluntary accreditation scheme, AGDIS participation approval, accreditation trustmark, identity/authentication levels | accreditation application/review, participation approval, compliance, incident handling, suspension/revocation | Provides clear separation between **service role**, **accreditation status**, **system participation**, **regulator**, and **operator**. Identity Exchange is useful as an orchestration/intermediary profile pattern. |
| **MOSIP** | Current 1.2.0 documentation reviewed | Resident, Registration actors, Authentication Partner/RP, Credential Provider, Device Provider, Partner Application, ID System | partner onboarding, approved policy, certificates/trust stores, platform governance | pre-registration, registration, processing, issuance, authentication, partner activation/deactivation | Useful operational validation of foundational-ID lifecycle and partner governance. Implementation modules and specialized partner types should not be promoted mechanically to Core. |
| **World Bank ID4D** | Current practitioner guide + 2025 Global Dataset | ID Authority / institutional mandate, foundational ID system, population/credential context | legal/regulatory framework, accountability, privacy, independent oversight, interoperability principles | birth-to-death coverage framing; registration, issuance, use and management indicators | Governance/rights/oversight are essential evaluation/context dimensions but should remain mostly Government profile concerns rather than Core identity entities. |

## 2. Additional global validation examples

Singapore Singpass and India Aadhaar were checked as validation examples. Singpass primarily reinforces already-covered OIDC OP/RP and assurance patterns; Aadhaar reinforces requesting-entity/intermediary authentication patterns. Because these did not materially change the candidate set beyond EUDI/UK/Australia/MOSIP plus the standards wave, they are not promoted into the curated evidence subset for this issue. This follows the saturation/bounded-review rule and avoids evidence-count inflation.

## 3. Cross-framework recurring semantics

The following patterns recur across multiple independent government/trust ecosystems and therefore deserve Gate-B consideration beyond simple vendor/jurisdiction mapping:

1. **Governed ecosystem / trust framework** — an explicit set of rules and conformance expectations governing participants.
2. **Participant/provider role** — services perform distinct identity, attribute, holding/wallet, orchestration/exchange, credential or relying roles.
3. **Registration / accreditation / certification status** — ecosystem trust depends on a participant's current governed status, not just on a bilateral trust relation.
4. **Registry / trusted-list information** — status is made discoverable through a governed registry/list.
5. **Assurance / confidence** — proofing, authentication, credentials/attributes and provider conformance can each carry different assurance semantics.
6. **Provenance and binding** — attributes/credentials are trusted partly because their source, binding and verification history can be communicated.
7. **Lifecycle** — issue, activate, maintain, suspend, revoke, recover, close, expire and re-check patterns recur for credentials, wallets/accounts and provider participation.
8. **Oversight / governance authority** — regulator, registrar, certification body, system operator and standards authority are distinct roles in mature ecosystems.
9. **User control / disclosure** — EUDI and UK holder-service models strengthen user-controlled sharing, selective disclosure and reuse, but these remain partly policy/privacy concerns.
10. **Intermediary / orchestration** — UK orchestration and Australian identity exchange show that identity information flow can be mediated by an ecosystem service distinct from IdP/RP.

## 4. Key non-equivalences / anti-conflation rules

- **Trust Anchor ≠ Trust Registry ≠ Trusted List ≠ Trust Framework.** A trust anchor is a cryptographic/authoritative validation root; a registry/list records governed participant/service status; a trust framework is the governing rule system.
- **Accreditation ≠ Certification ≠ Registration ≠ Recognition.** These may be related governance events/statuses, but legal meaning and responsible authority differ by ecosystem.
- **Wallet Provider ≠ Holder ≠ Holder Service Provider.** Provider, user role and service/application role must remain ontologically distinct.
- **Identity Service Provider ≠ PID Provider ≠ Credential Issuer.** They may map or co-occur in implementations, but their responsibilities differ.
- **Attribute ≠ Attestation ≠ Credential.** An attribute is a property/information item; an attestation/credential is an information object that makes or carries claims/attributes with provenance/status.
- **Regulator ≠ System Administrator ≠ Registrar ≠ Conformity Assessment Body.** Governance and operational responsibilities should not collapse into a generic `IdentityProvider`.
- **Legal Identity ≠ Digital Identity.** Government systems establish or rely on a legally recognized identity substrate; CM4DI's digital representation should remain conceptually distinct from the real/legal identity basis.

## 5. Main implications for CM4DI before Gate B

### High-confidence gaps to carry forward
- generic `TrustFramework` / governed ecosystem context;
- `TrustRegistry` or governed participant-status registry;
- generic `ParticipantStatus` / `CertificationOrAccreditationStatus` pattern;
- `GovernanceAuthority` / `OversightAuthority` profile pattern;
- `LegalIdentity` or a carefully scoped legal-identity basis distinction;
- `Pseudonym` as a candidate identifier subtype or derived identifier;
- explicit provenance/binding semantics for identity attributes and credentials;
- generic lifecycle-event/state pattern reusable across credential, holder account/wallet and ecosystem participation;
- intermediary/orchestration/exchange role pattern, likely profile-first.

### Strong profile candidates
- EUDI Wallet Provider, PID Provider, Attestation Provider, Registrar, Wallet Unit, Wallet Unit Attestation, registration/access certificates;
- UK Holder/Orchestration/Component Service Provider roles and DVS Register mapping;
- Canada Trust Registry participant/certification constructs;
- Australia Identity Exchange Provider, Digital ID Regulator, AGDIS participation, accreditation Trustmark;
- MOSIP Registration/Partner specializations and implementation modules.

### Explicitly not admitted yet
No candidate in this document is a Core class merely because it appears in legislation or a major national system. Gate B must still test cross-framework recurrence, UFO category, competency-question value, and interaction with existing CM4DI concepts.

## 6. Source set

Curated provenance records are in `GOVERNMENT_EVIDENCE_REGISTRY.csv` (`CM4DI-EVID0030`–`CM4DI-EVID0045`). The retained set prioritizes authoritative legal texts, current official framework pages, official architecture documents, final framework modules and the World Bank's current global evidence. Lower-value duplicative national examples were reviewed but not retained when they did not add semantic distinctions.