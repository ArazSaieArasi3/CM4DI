# CM4DI Relational Conceptual Model v2

Status: **candidate downstream data realization; not a canonical database schema**.

## Purpose
Define how a relational implementation may persist CM4DI-aligned data while preserving ontological distinctions and provenance. The relational model is an explicit research/product artifact, not a substitute for the ontology.

## Design principles

1. Ontology identity and database identity are different: a primary key is not an ontological Identifier by definition.
2. `IdentitySubject`, `DigitalIdentity`, `Account` and `UserProfile` remain distinct even if a product joins them frequently.
3. External identifiers retain source/system/scheme provenance.
4. Lifecycle events and statuses are temporal records, not mutable strings only.
5. Claims/evidence/provenance are modeled explicitly enough for audit and evaluation.
6. Product/vendor objects are stored through mapping/adapter tables rather than changing canonical concept names.
7. Bounded Context ownership guides schema ownership, but deployment may use one or several physical databases.
8. No Domain/Bounded Context is named with `and`, `&`, or slash-composed semantic centers.

## Candidate relational areas

### Identity Semantics

- `identity_subject_ref`
  - internal surrogate key
  - external/entity type reference
  - subject kind/source metadata
  - no assumption that every subject is a person
- `digital_identity`
  - stable internal key
  - identity-subject reference
  - identity-context reference
  - lifecycle metadata
- `identifier`
  - value, scheme, issuer/source, scope, validity
- `identity_context`
  - semantic context identifier and description
- `identity_attribute`
  - normalized attribute concept/value representation
- `claim`
  - subject reference, predicate/attribute reference, asserted value, issuer/source, provenance

### Identity Assurance

- `evidence_artifact`
  - artifact reference, type/role, source, hash/URI, provenance metadata
- `proof_usage`
  - evidence artifact playing Proof role in a specific verification context
- `identity_binding`
  - subject, representation/credential/authenticator target, validity, basis
- `binding_evidence`
  - many-to-many binding-to-evidence relation
- `assurance_assessment`
  - dimension, target, level/value, framework, evaluator, evidence references
- `identity_proofing_event`
- `enrollment_event`

### Credential Lifecycle

- `credential`
  - credential type/profile, issuer role reference, subject/holder references, issued-at, expiry
- `credential_claim`
- `credential_status`
  - current derived status if needed
- `credential_status_history`
  - append-only lifecycle status/event history
- `credential_lifecycle_event`
  - issuance, suspension, revocation, expiry, recovery/other profile events

### Authentication

- `authentication_event`
  - actor/subject/principal references where known
  - time/context/channel/provider
- `authentication_authenticator`
- `authentication_result`
  - explicit success/failure/result metadata
- `session`
  - separate post-authentication lifecycle; start/end/revocation/context

### Authorization

- `principal`
  - contextual principal representation; link to account/application/workload/agent as appropriate
- `resource`
- `action`
- `permission`
- `permission_bundle`
- `access_grant`
  - principal, permission/bundle, resource/scope, effective/expiry, grant source
- `delegation`
  - delegator, delegatee, scope, permissions/actions, validity
- `authorization_request`
- `authorization_context`
- `authorization_result`
- `access_policy`
- `access_condition`
- `access_group`
- `group_membership`

### Identity Administration

- `account`
  - local account ID, subject/digital-identity relationship, administrative domain, lifecycle status
- `user_profile`
- `identity_source`
- `identity_store`
- `administrative_domain`
- `application`
- `application_registration`
- `provisioning_connection`
- `provisioning_event`
- `attribute_mapping`
- `linked_account`
  - source account, target account, link basis/status; never implies entity equality

### Federation

- `federation_relationship`
- `federation_connection`
  - protocol/profile, issuer/provider, relying side, metadata/config references
- `identity_broker_assignment`
- `relying_party_registration`
- `federation_transaction_ref`
  - optional protocol transaction trace separate from canonical Federation relationship

### Credential Exchange

- `wallet_registration`
- `holder_relationship`
- `presentation_request`
- `credential_presentation_event`
- `verifiable_presentation_artifact`
- `verification_method`
- `verifiable_data_registry_ref`
- `selective_disclosure_record`

### Workload Identity

- `workload`
- `runtime_instance`
- `service_account`
- `service_principal`
- `managed_identity`
- `node_attestation_event`
- `workload_attestation_event`
- `trust_domain`
- `trust_bundle_ref`
- `svid_credential`
- `temporary_credential`
- `token_exchange_event`

### Device Identity

- `device`
- `device_identity_record`
- mapping tables to account/principal/authenticator roles rather than collapsing them into the device row

### Agent Identity

- `software_agent`
- `ai_agent_profile`
- `agent_identity`
- `agent_sponsor_assignment`
- agent authorization/delegation references reuse Authorization structures

### Trust Governance

- `trust_framework`
- `governance_framework`
- `trust_registry`
- `trusted_list`
- `trust_anchor_ref`
- `trust_chain_ref`
- `governance_actor_role`
- `certification_event`
- `accreditation_event`
- `ecosystem_participation`
- `participant_status_history`
- `trust_assessment`
- `trust_reference`

### Government Identity

- `legal_identity_ref`
- `person_identification_data`
- `government_attestation`
- `identity_service_provider_registration`
- jurisdiction/profile mapping tables

## Cross-cutting provenance tables

- `external_system`
- `external_object_reference`
- `source_document`
- `source_assertion`
- `ontology_mapping`
- `standard_mapping`
- `concept_instance_type`
- `audit_event`

These permit one application object to retain links to Entra, AWS, Google, Okta, EUDI or other external representations without treating those records as identical.

## Key relational constraints to preserve ontology meaning

- `digital_identity.identity_subject_id` must not be replaced by an account foreign key as if Account were the subject.
- account-linking tables must not enforce semantic identity/equality between source accounts.
- credential status should retain history rather than overwriting all lifecycle evidence.
- authorization decisions are event results and must not be reused as durable access grants.
- federation relationships must not be represented solely as provisioning connections.
- service principals, service accounts, managed identities and workloads require separate identifiers/tables or explicit typed representation.
- trusted-list membership, ecosystem participation and cryptographic trust-anchor references must not share one overloaded trust table.

## Next implementation work

Issue #73 will compare this conceptual model with real directory/store schemas. Issue #76 will produce the machine-readable ontology↔relational crosswalk and traceability chain. Physical database selection and SQL DDL are deferred until required queries, scale, temporal/provenance needs and architecture quality scenarios are clearer.