# CM4DI Journal V2 — Standards Status and Supersession Map

**Verified through:** 2026-08-19

This document prevents obsolete versions and active drafts from being silently treated as the current normative baseline.

## Stable-current baseline

| Family | Stable/current baseline used by CM4DI | Relevant predecessor/update relationship | Treatment |
|---|---|---|---|
| ISO identity terminology | ISO/IEC 24760-1:2025 | 2019 edition and 2023 amendment withdrawn | Use 2025 |
| ISO identity architecture | ISO/IEC 24760-2:2025 | 2015 edition withdrawn | Use 2025 |
| ISO identity practice | ISO/IEC 24760-3:2025 | earlier edition replaced | Use 2025 |
| ISO authentication assurance | ISO/IEC 29115:2013 | current but marked to be revised by CD 29115.2 | Use 2013 cautiously + monitor replacement |
| ISO access management | ISO/IEC 29146:2024 | replaces earlier edition | Use 2024 |
| ISO mobile eID architecture | ISO/IEC 23220-1:2023 | first edition | Use 2023 |
| ISO mobile eID data model | ISO/IEC TS 23220-2:2026 | 2024 edition withdrawn | Use 2026 |
| ISO mobile eID issuance | ISO/IEC TS 23220-3:2026 | first edition | Use 2026 |
| ISO mobile eID operation | ISO/IEC TS 23220-4:2026 | first edition | Use 2026 |
| ISO mobile eID trust | no stable baseline yet | CD TS 23220-5 at stage 30.92 | Monitor only |
| ISO mDL | ISO/IEC 18013-5:2021 | current but marked to be revised | Use 2021 + monitor successor |
| NIST digital identity | SP 800-63-4 family, Jul 2025 | supersedes Revision 3 / A/B/C 2020-updated set | Use Revision 4 |
| W3C VC model | VC Data Model v2.0, May 2025 | v2 stable; later work may evolve | Use v2.0 |
| W3C DID | DID v1.0, Jul 2022 | DID v1.1 is Candidate Recommendation, Mar 2026 | Use 1.0; monitor 1.1 |
| W3C credential integrity | VC Data Integrity 1.0, May 2025 | v1.1 is Working Draft, Apr 2026 | Use 1.0; monitor 1.1 |
| W3C WebAuthn | Level 2 Recommendation, Apr 2021 | Level 3 Candidate Recommendation, May 2026 | Use L2; monitor L3 |
| W3C browser credentials | no stable Recommendation | Digital Credentials API Working Draft, Jun 2026 | Monitor only |
| OpenID Connect | Core 1.0 incorporating Errata Set 2, Dec 2023 | corrections over original Final | Use Errata 2 text |
| OpenID4VP | 1.0 Final, Jul 2025 | replaces draft line | Use Final |
| OpenID4VCI | 1.0 Final, Sep 2025 | replaces draft line | Use Final |
| OpenID4VC HAIP | 1.0 Final, Dec 2025 | profiles OID4VC + SD-JWT VC + ISO mdoc | Use Final as profile evidence |
| OpenID Federation | 1.1 Final, May 2026 | current Final line | Use 1.1 |
| OpenID AuthZEN | Authorization API 1.0 Final, Jan 2026 | replaces draft line | Use Final |
| OpenID Identity Assurance | 1.0 Final with 2026 errata process | errata activity ongoing/approved through Foundation process | Track latest approved errata when manuscript freezes |
| OAuth security | RFC 9700 / BCP 240, Jan 2025 | updates RFC 6749, 6750, 6819 security guidance | Keep OAuth 2.0 foundations; apply BCP 240 security baseline |
| SCIM core/protocol | RFC 7643 + RFC 7644 | RFC 9865 (2025) and RFC 9967 (2026) update the family | Use base RFCs plus applicable updates |
| JWT | RFC 7519 | updated by RFC 7797 and RFC 8725 | Use as representation/mapping evidence |
| SAML | SAML 2.0 OASIS Standard + maintained errata | stable legacy federation baseline | Use as representative federation standard |
| XACML | XACML 3.0 + Errata 01 | supersedes XACML 2.0 | Use 3.0 + Errata |
| XACML JSON | JSON Profile 1.1 OASIS Standard, Jun 2019 | supersedes profile 1.0 | Use 1.1 |
| FIDO CTAP | CTAP 2.3 Proposed Standard, Feb 2026 | 2.3.1 Working Draft exists | Use 2.3; monitor 2.3.1 |

## Draft-handling rule

A draft is retained only when it signals a likely future semantic change that could invalidate a near-term journal claim. Draft content **must not** be the sole justification for a Core concept. The journal freeze must perform another status check for all entries marked `Monitor`.

## Supersession risk for the journal

Highest monitoring priority before submission:

1. ISO/IEC 29115 successor work.
2. ISO/IEC 23220-5 trust models.
3. ISO/IEC 18013-5 next edition.
4. DID v1.1 and DID-resolution work.
5. WebAuthn Level 3.
6. W3C Digital Credentials API.
7. OpenID Identity Assurance errata.
8. FIDO CTAP 2.3.x maintenance.

These items are also covered by the monthly digital-identity standards monitoring task.