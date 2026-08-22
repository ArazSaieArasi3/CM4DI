# P02 — Wallet / Verifiable Credentials Profile

## Purpose
Represent wallet, verifiable-credential, mdoc and decentralized-identifier ecosystems while preserving a protocol-neutral CM4DI Core.

## Core reuse
- `Issuer`, `Holder` and `CredentialPresentationVerifier` are contextual profile roles.
- Holder is not assumed to equal `IdentitySubject`; a credential can be held/presented by an authorized party different from its subject.
- W3C VC, ISO mdoc, EUDI PID/EAA and similar artifacts specialize/map to Core `Credential`.
- DID and related decentralized identifiers map to Core `Identifier`; DID control remains P02 `Controller` semantics.
- `CredentialPresentation` is an event distinct from Core `Authentication`.
- Cryptographic proofs, signatures and verification material may play Core `Evidence`/`Proof` roles but remain profile mechanisms.

## Profile concepts
P02 contributes 12 governed concepts: Issuer, Holder, CredentialPresentationVerifier, Wallet, HolderService, CredentialPresentation, PresentationRequest, Controller, VerificationMethod, VerifiableDataRegistry, SelectiveDisclosure and VerifiablePresentation.

## Representative external alignments
- W3C VC Data Model 2.0: Issuer/Holder/Verifier -> contextual P02 roles; VerifiableCredential -> Core `Credential`; VerifiablePresentation -> P02 `VerifiablePresentation`; credentialSubject -> Core `IdentitySubject` relation.
- W3C DID Core: DID -> Core `Identifier`; Controller -> P02 `Controller`; VerificationMethod -> P02 `VerificationMethod`.
- OpenID4VCI: CredentialIssuer -> P02 `Issuer`; issuance transaction -> Core `CredentialIssuance`; wallet -> P02 `Wallet`.
- OpenID4VP: Verifier -> P02 `CredentialPresentationVerifier`; presentation request -> `PresentationRequest`; wallet/holder presentation -> `CredentialPresentation`.
- ISO/IEC 18013-5 and 23220 series: mdoc/mobile eID credential artifacts map to Core `Credential`; reader/verifier roles map to P02 verifier role; installation/issuance/operational semantics are profile lifecycle mappings.
- EUDI wallet: wallet/provider/PID/EAA semantics are split across P02 and P04 rather than collapsed into one core vocabulary.

## Anti-conflation invariants
`Holder != IdentitySubject`; `Controller != Holder`; `CredentialPresentation != Authentication`; `VerifiablePresentation != Credential`; `DID != DigitalIdentity`; `VerificationMethod != Authenticator`; `SelectiveDisclosure != Consent`; `Wallet != DigitalIdentity`.

## Minimum scenario
A party plays `Issuer` and performs Core `CredentialIssuance` for a `Credential` about an `IdentitySubject`. A different party may play `Holder` and operate a `Wallet`. A `CredentialPresentationVerifier` sends a `PresentationRequest`; the holder participates in `CredentialPresentation`, producing a `VerifiablePresentation`. Claims and evidence/proof are evaluated without redefining the Core credential or authentication semantics.

## Wave-7 formalization expectation
P02 is a separate ontology module importing the Core. Protocol-specific request/response/token terms remain mappings or narrowly scoped profile classes; cryptographic details are constrained through SHACL/mappings rather than overloading the Core.