# CM4DI Journal V2 — DDD Context Map

## Status
Canonical strategic DDD context map introduced by #50 after Gate C and Wave 6. This is an organizational/model-ownership refinement; it does not change the identity of the frozen semantic concepts.

## Global problem space
**Digital Identity Management** (`CM4DI-D0000`) is the overall Domain. Its fifteen subdomains are owned by thirteen Bounded Contexts.

## Core integration rule
`Identity Semantics Context` is the canonical **Published Language / Shared Kernel** for subject, representation and identity-information semantics. Other bounded contexts reuse those concepts without redefining their identity criteria.

External standards, protocols and vendor models do **not** become internal bounded contexts. They enter through explicit mappings and **Anticorruption Layer** translations where their terminology would otherwise distort CM4DI semantics.

## Context relationships

| Upstream | Downstream | DDD relationship | Contract |
|---|---|---|---|
| Identity Semantics Context | all contexts | Published Language / Shared Kernel | Reuse IdentitySubject, DigitalIdentity, Identifier, IdentityContext, IdentityAttribute and Claim semantics without redefinition. |
| Identity Assurance Context | Credential Lifecycle Context | Customer Supplier | Credentials may use Evidence, Proof, Binding and AssuranceAssessment; credential lifecycle does not redefine assurance. |
| Identity Assurance Context | Authentication Context | Customer Supplier | Authentication may consume Evidence/Authenticator bindings and emit dimension-specific assurance; Authentication is not IdentityProofing. |
| Credential Lifecycle Context | Credential Exchange Context | Customer Supplier | Exchange presents/uses credentials but does not own issuance/status identity criteria. |
| Identity Administration Context | Federation Context | Customer Supplier | Federation may rely on accounts, applications and administrative domains; Provisioning remains separate. |
| Authentication Context | Federation Context | Customer Supplier | Federation may transport/mediate authentication results but is not Authentication itself. |
| Trust Governance Context | Federation Context | Customer Supplier | Federation trust chains/framework participation are governed without collapsing into TrustAssessment. |
| Trust Governance Context | Credential Exchange Context | Customer Supplier | Credential ecosystem registries/trusted lists may support verification; cryptographic verification remains distinct from governance status. |
| Authorization Context | Workload Identity Context | Published Language | Workload principals, grants and permissions reuse generic authorization semantics. |
| Identity Assurance Context | Workload Identity Context | Customer Supplier | Attestation artifacts may play Evidence/Proof and ground IdentityBinding. |
| Credential Lifecycle Context | Workload Identity Context | Customer Supplier | SVID and temporary credentials specialize/reuse generic Credential semantics. |
| Trust Governance Context | Workload Identity Context | Related Context / ACL boundary | SPIFFE TrustDomain/TrustBundle remain technical trust constructs and are not silently retyped as governance TrustFramework/TrustRegistry. |
| Authentication Context | Device Identity Context | Published Language | Device may play Authenticator while remaining a Device kind. |
| Authorization Context | Device Identity Context | Published Language | Device may play Principal; DeviceIdentityRecord does not become the Device. |
| Authorization Context | Agent Identity Context | Published Language | Agent access uses Principal, AccessGrant and Delegation. |
| Trust Governance Context | Agent Identity Context | Customer Supplier | Sponsor/accountability and governed participation may be linked without turning agents into governance artifacts. |
| Identity Assurance Context | Government Identity Context | Customer Supplier | Government proofing/attestation reuses evidence and assurance semantics. |
| Credential Lifecycle Context | Government Identity Context | Customer Supplier | Government attestations may specialize/map to Credentials where appropriate. |
| Credential Exchange Context | Government Identity Context | Customer Supplier | Government credentials may be exchanged/presented using wallet/VC mechanisms without making Wallet a government-domain concept. |
| Trust Governance Context | Government Identity Context | Customer Supplier | Legal/government identity ecosystems use governance roles, certification and participation status while LegalIdentity remains separate. |

## Profile relationship
Profiles are **cross-context integration views**, not Domains and not Bounded Contexts. P01–P04 may compose concepts from several contexts for standards/platform interoperability scenarios.

## Formal ontology relationship
An OWL module is a packaging/formalization decision. It MAY align to one Bounded Context or package several tightly coupled contexts, but no automatic identity is asserted between `Domain`, `Bounded Context`, `Profile`, or `OWL module`.

## Non-scope boundary
Social Identity remains outside `Digital Identity Management`; only explicit bridge mappings such as social login/federation or organizational affiliation claims may cross this boundary.