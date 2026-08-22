# CM4DI Journal V2 — Profile Integration Matrix

## DDD status
Revalidated by #50. Profiles are cross-domain integration views. Their stable IDs remain P01–P04, but they are not Domains, Bounded Contexts or predetermined OWL modules.

## Profile composition principle
Every profile composes canonical DDD subdomains and Bounded Contexts through the contracts in `../ddd/DOMAIN_PROFILE_MATRIX_v2.csv` and `../ddd/PROFILE_DOMAIN_CONTRACTS_v2.md`.

| Profile | Canonical label | Primary responsibility | Main Domain composition | Prohibited collapse |
|---|---|---|---|---|
| P01 | Enterprise Identity Profile | Enterprise IAM, account administration, federation and access-management integration | Identity Administration; Federation; Authentication; Authorization plus canonical identity/evidence/trust semantics | Account=Subject; Session=AuthResult; IAMRole=UFORole; Profile=Domain |
| P02 | Verifiable Credential Profile | Credential lifecycle/exchange, wallet, DID/VC and presentation integration | Credential Management; Credential Exchange plus Identity Representation/Information/Evidence and Trust Governance | Holder=Subject; Presentation=Authentication; DID=DigitalIdentity; Wallet=Domain |
| P03 | Technical Identity Profile | Workload, device and agent identity integration | Workload Identity; Device Identity; Agent Identity plus credential/authentication/authorization/admin/trust dependencies | Workload=ServiceAccount; Device=Authenticator; MachineIdentity superclass; TechnicalIdentity=single Domain |
| P04 | Governed Identity Profile | Trust governance, legal/government identity and assurance integration | Trust Governance; Government Identity plus Identity Evidence/Establishment/Credential Management | TrustAssessment=TrustFramework; LegalIdentity=DigitalIdentity; Certification=Enrollment; GovernmentIdentity=TrustGovernance |

## Cross-profile bridge decisions

### Enterprise workload identity — P01 + P03
- Application/ApplicationRegistration are Identity Administration concepts surfaced mainly by P01.
- Workload, ServicePrincipal and ManagedIdentity belong to Workload Identity surfaced by P03.
- Federation configuration belongs to Federation.
- Principal/AccessGrant/Authentication/Authorization are consumed from canonical contexts.
- PASS: no domain or concept identity collision.

### EUDI wallet — P02 + P04
- Wallet, holder and presentation interaction belong to Credential Exchange.
- Credential issuance/status belongs to Credential Management.
- PID/legal/government attestation belongs to Government Identity.
- provider status/trust lists/certification belong to Trust Governance.
- PASS: P02/P04 remain views over distinct contexts.

### Government enterprise federation — P01 + P04
- federation/broker interaction belongs to Federation.
- account/session/provisioning ownership remains Identity Administration/Authentication.
- governed provider participation/certification/registry belongs to Trust Governance.
- legal identity semantics belong to Government Identity.
- PASS: provider role occurrences remain distinct.

### Agent access — P03 + P01
- agent representation belongs to Agent Identity.
- enterprise application/account administration may be consumed from Identity Administration.
- delegated authority belongs to Authorization `Delegation`; autonomous rights to `AccessGrant`.
- PASS: no AgentIdentity/AIAgent or Sponsor/Delegator conflation.

### SPIFFE and governed trust — P03 + P04
- TrustDomain/TrustBundle belong to Workload Identity technical trust semantics.
- TrustFramework/TrustRegistry/certification belong to Trust Governance.
- explicit `related` mappings may connect them; subtype/equivalence is prohibited.
- PASS: technical and institutional trust remain separated.

### Device as subject and authenticator — P03
- Device belongs to Device Identity.
- Authenticator role belongs to Authentication.
- DeviceIdentityRecord remains a representation/administrative artifact.
- PASS: role and kind identity preserved.

## Re-executed cross-profile scenario checks
1. Employee SSO — **PASS**.
2. EUDI PID presentation to enterprise relying party — **PASS**.
3. SPIFFE workload accessing cloud resource — **PASS**.
4. AI agent delegated access to enterprise API — **PASS**.
5. Government-certified wallet provider — **PASS**.
6. Device used both as subject and authenticator — **PASS**.

## Wave-7 module rule
The earlier default of publishing Core plus four profile ontologies is **superseded as an automatic assumption**. Wave 7 MUST derive formal module boundaries from the DDD Bounded Context map, semantic dependency cohesion and OWL import-cycle constraints. Profiles remain publishable views/mapping bundles and MAY be materialized as aggregate ontology entrypoints, but `Profile != Domain != Bounded Context != OWL module`.