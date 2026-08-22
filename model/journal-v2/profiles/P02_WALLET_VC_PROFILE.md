# P02 — Verifiable Credential Profile

**Legacy label:** Wallet / Verifiable Credentials  
**DDD status:** Cross-domain integration Profile; not a Domain or Bounded Context.

## Purpose
Represent wallet, verifiable-credential, mdoc and decentralized-identifier ecosystems while preserving protocol-neutral CM4DI semantics.

## Domain composition
P02 composes Identity Representation, Identity Information, Identity Evidence, Credential Management, Credential Exchange and Trust Governance.

## Core and Domain reuse
- `Issuer` belongs primarily to Credential Management; `Holder` and `CredentialPresentationVerifier` belong to Credential Exchange.
- Holder is not assumed to equal `IdentitySubject`.
- W3C VC, ISO mdoc, EUDI PID/EAA and similar artifacts specialize/map to Credential Management `Credential`.
- DID and related decentralized identifiers map to Identity Representation `Identifier`; controller/verification methods remain Credential Exchange semantics.
- `CredentialPresentation` belongs to Credential Exchange and is distinct from Authentication.
- Cryptographic proofs, signatures and verification material may play Identity Evidence `Evidence`/`Proof` roles but remain ecosystem mechanisms.
- Trusted registry/list semantics crossing into governance are explicit Trust Governance dependencies.

## Profile concepts
P02 contributes 12 governed concepts. Their primary Domain ownership is maintained in `../ddd/CONCEPT_DOMAIN_ASSIGNMENT_v2.csv`.

## Representative external alignments
- W3C VC Data Model 2.0: Issuer/Holder/Verifier map to contextual roles; VerifiableCredential -> `Credential`; VerifiablePresentation -> P02 artifact; credentialSubject -> `IdentitySubject` relation.
- W3C DID Core: DID -> `Identifier`; Controller -> `Controller`; VerificationMethod -> `VerificationMethod`.
- OpenID4VCI: CredentialIssuer -> `Issuer`; issuance transaction -> `CredentialIssuance`; wallet -> `Wallet`.
- OpenID4VP: Verifier -> `CredentialPresentationVerifier`; request -> `PresentationRequest`; presentation -> `CredentialPresentation`.
- ISO/IEC 18013-5 and 23220: credential artifacts map to Credential Management; reader/verifier interaction maps to Credential Exchange.
- EUDI: wallet/exchange semantics are P02 while legal identity/governance semantics are composed from P04 domains.

## Anti-conflation invariants
`Holder != IdentitySubject`; `Controller != Holder`; `CredentialPresentation != Authentication`; `VerifiablePresentation != Credential`; `DID != DigitalIdentity`; `VerificationMethod != Authenticator`; `SelectiveDisclosure != Consent`; `Wallet != DigitalIdentity`.

## Minimum scenario
Credential issuance uses Credential Management. Storage/control/presentation uses Credential Exchange. Claims/evidence reuse Identity Information and Identity Evidence. Trust lists or governed status consume Trust Governance without collapsing governance into verification.

## Wave-7 formalization expectation
OWL packaging is derived from Bounded Context ownership and dependency analysis; P02 is not automatically one ontology module. Protocol-specific terms remain mappings or narrowly scoped formal constructs.