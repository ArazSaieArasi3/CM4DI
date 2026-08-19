# CM4DI Journal V2 — Evaluation Dataset and Test-Suite Portfolio

**Status:** Gate-B decision support; no ontology admission or final evaluation design yet.  
**Review date:** 2026-08-19

## Decision principle

No single public dataset spans proofing, authentication, authorization, federation, wallet credentials, government trust, workload identity and agent identity. Evaluation therefore uses a **triangulated portfolio**: conformance/test artefacts for standards semantics, operational reference implementations for scenario realism, and a small number of datasets for empirical instantiation/query evaluation.

## Recommended primary portfolio

### P1 — W3C VC 2.0 / DID conformance artefacts
Use official W3C VC/DID test suites and implementation reports to validate Wallet/VC profile mappings and competency questions around issuer/holder/verifier, credential subject, status, controller and verification material.

**Purpose:** semantic/conformance mapping, not empirical population validation.

### P2 — OpenID Certification conformance suite
Use the authoritative OpenID conformance suite to select representative OIDC/federation/OID4VC transaction traces and expected behaviors.

**Purpose:** protocol-to-ontology mapping and interoperability scenarios.

### P3 — EUDI Wallet Reference Implementation
Use a bounded end-to-end wallet scenario (issuance → holding → presentation → verifier/relying-party interaction) to test whether CM4DI can represent the same scenario without importing EUDI implementation classes into Core.

**Purpose:** cross-layer Government + Wallet/VC profile validation.

### P4 — SPIRE reference implementation
Use a workload-registration/attestation/SVID issuance/presentation scenario, optionally including trust-domain federation.

**Purpose:** non-human identity profile validation and explicit test of Workload ≠ Identifier ≠ Credential ≠ Attestation ≠ TrustDomain.

### P5 — LANL User–Computer Authentication dataset
Use a reproducible sample rather than the full 708M-event corpus for ontology instantiation and SPARQL CQ execution.

**Purpose:** large-scale authentication-event graph and temporal trace evaluation.

### P6 — Zenodo Risk-Based Authentication dataset
Use stratified/reproducible samples containing successful and failed attempts plus context/risk features.

**Purpose:** AuthenticationAttempt/AuthResult, Account, Device/Client context and risk-context CQs.

### P7 — World Bank ID4D Global Dataset 2025
Use country/system indicators to instantiate selected Government Profile concepts and evaluate cross-country queries about official-ID/digital-ID capability and remote authentication availability.

**Purpose:** government/digital-ID contextual coverage; not transaction-level evaluation.

## Secondary/optional portfolio

- Global Findex 2025 world microdata with the ID4D questionnaire module can complement ID4D with person-level ownership/use data if individual-level government-ID questions materially improve the final evaluation.
- Keycloak can provide a reproducible enterprise/federation scenario if a live/open IAM scenario is needed beyond standards mappings.
- MOSIP reference implementation/functional tests can provide a foundational-ID lifecycle scenario if Government Profile evaluation needs executable workflow evidence beyond ID4D aggregate data.

## Why Kaggle is not selected

Kaggle is useful as a discovery surface, but no Kaggle-hosted copy is needed in the primary portfolio because higher-provenance originals are available for the selected authentication and government-ID evidence. If a Kaggle dataset is considered later, its upstream origin, license and transformation history must be established before use.

## Dataset-to-ontology limits

Datasets are **not ontology authorities**. They can:
1. reveal operational entity/event/attribute patterns;
2. instantiate already justified concepts;
3. test competency questions and mappings;
4. expose missing representational capacity.

They cannot by themselves justify a Core class merely because a column or entity label exists.

## Reproducibility policy

For large datasets, commit only code/configuration, sample-selection rules, checksums/metadata where permitted, mapping tables and derived non-sensitive results. Do not commit multi-GB raw datasets to the CM4DI repository. Preserve source DOI/URL, license/access terms, retrieval date and deterministic sample recipe.

## Gate-D implication

At Gate D, choose a minimal executable evaluation set from P1–P7 based on the final Core/Profile scope. Recommended default is: one VC/wallet conformance scenario, one enterprise/federation scenario, one workload scenario, LANL authentication sample, RBA sample, and ID4D government-profile sample.