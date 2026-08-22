# CM4DI Journal V2 — Profile Integration Matrix

## Module dependency principle
All profiles import/reuse the frozen Gate-C Core. Cross-profile reuse is allowed only through explicit mappings or declared dependencies and MUST NOT alter Core identity criteria.

| Profile | Primary responsibility | Core anchors | Allowed cross-profile dependencies | Prohibited collapse |
|---|---|---|---|---|
| P01 Enterprise/Federation | Accounts, federation, provisioning, sessions, enterprise access constructs | IdentitySubject, DigitalIdentity, Authentication, Principal, Permission, AccessGrant, Authorization | P03 machine principals/accounts; P04 governance/trust; P02 only where enterprise wallet federation is needed | Account=Subject; Session=AuthResult; IAMRole=UFORole |
| P02 Wallet/VC | Credential issuance, holding, wallet, presentation, DID/verification methods | Credential, Claim, Evidence/Proof, Identifier, CredentialIssuance, Verifier | P04 EUDI/government attestations; P01 federation where wallet authenticates to enterprise systems | Holder=Subject; Presentation=Authentication; DID=DigitalIdentity |
| P03 Machine/Workload/Device/Agent | Non-human bearers, workload/device/agent representations, attestation | IdentitySubject, Principal, DigitalIdentity, Credential, Evidence, IdentityBinding, Delegation, AccessGrant | P01 Account/Application/Federation; P04 technical/governed trust where required | Workload=ServiceAccount; Device=Authenticator; MachineIdentity superclass |
| P04 Trust/Assurance/Government | Governance, trust registries/anchors, assurance mappings, government/legal identity | TrustAssessment, TrustReference, AssuranceAssessment, IdentitySubject, Credential | P02 wallet/EUDI interactions; P01 broker/federation; P03 technical trust domain as related construct | TrustAssessment=TrustFramework; LegalIdentity=DigitalIdentity; Certification=Enrollment |

## Cross-profile bridge decisions

### Enterprise workload identity — P01 + P03
- `Application`/`ApplicationRegistration` are P01.
- executing `Workload` is P03.
- `ServicePrincipal`/`ManagedIdentity` are P03 representation/principal patterns.
- federation configuration may be P01 `FederationConnection` while workload bearer semantics remain P03.
- Core `Principal`, `AccessGrant`, `Credential`, `Authentication` and `Authorization` are shared anchors.

### EUDI wallet — P02 + P04
- wallet, holder, presentation and verification interaction are P02.
- PID, regulated attestation, trust framework, provider certification and trusted-list semantics are P04.
- Core `Credential`, `Claim`, `IdentitySubject`, `AssuranceAssessment`, `TrustReference` connect both profiles.

### Government enterprise federation — P01 + P04
- federation/broker/session/provisioning are P01.
- governed provider participation/certification/registry are P04.
- a provider may play P01 federation roles while simultaneously participating in a P04 governed ecosystem; these are distinct role occurrences.

### Agent access — P03 + P01
- agent/workload identity representation belongs to P03.
- enterprise application/account/session constructs may be reused from P01 when a platform requires them.
- delegated authority always reuses Core `Delegation`; autonomous rights reuse `AccessGrant`.

### SPIFFE and governed trust — P03 + P04
- SPIFFE `TrustDomain` and `TrustBundle` remain P03 technical identity/trust constructs.
- P04 `TrustFramework`, `TrustRegistry`, certification and governance do not subsume them.
- explicit `related` mappings may be added where an organization governs a SPIFFE deployment, but no subtype/equivalence is implied.

## Cross-profile scenario checks
1. **Employee SSO:** P01 only + Core — PASS.
2. **EUDI PID presentation to enterprise RP:** P02 + P04 + P01 RP/federation hooks — PASS without Core extension.
3. **SPIFFE workload accessing cloud resource:** P03 + optional P01 federation + Core authorization — PASS.
4. **AI agent delegated access to enterprise API:** P03 + P01 application/session + Core Delegation/Authorization — PASS.
5. **Government-certified wallet provider:** P04 governance + P02 wallet provider/holder-service semantics — PASS.
6. **Device used both as subject and authenticator:** P03 + Core roleMixins — PASS without identity collapse.

## Module rule for Wave 7
Formal modules SHOULD be published as Core plus four profile ontologies with explicit imports. Shared profile concepts MUST be promoted to Core only through a future governed semantic change, never merely because two profiles reuse them.