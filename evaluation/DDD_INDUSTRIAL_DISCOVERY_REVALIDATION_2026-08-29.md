# DDD Industrial Discovery Revalidation — 2026-08-29

## Purpose
Re-check the current CM4DI DDD problem-space decomposition against newly seeded operational IAM/SSO evidence before Source Completeness and formal-module freeze.

## Inputs
- `model/journal-v2/ddd/DOMAIN_REGISTRY_v2.csv`
- `model/journal-v2/ddd/BOUNDED_CONTEXT_REGISTRY_v2.csv`
- `evidence/industrial/IAM_SSO_PRODUCT_CATALOG.csv`
- official documentation sampled from AWS, Microsoft Entra, Google Cloud, Okta, Auth0, Keycloak, ZITADEL and related products.

## Naming control
All current canonical Domain and Bounded Context labels pass the naming rule: no `and`, no `&`, and no slash-composed multi-domain semantic center. Product names and external source titles are exempt because they are not CM4DI Domain names.

## Findings by Domain

| Domain | Initial industrial finding | Decision |
|---|---|---|
| Identity Representation | Product stacks consistently distinguish a represented user/service/device from local account/principal objects, although terminology varies. | RETAIN |
| Identity Information | Profile/claim/attribute models recur across OIDC, directories and IAM products. | RETAIN |
| Identity Evidence | Product docs expose attestation, proof, verification and assurance evidence but often mix them operationally; ontology separation remains useful. | RETAIN |
| Identity Establishment | NIST proofing/enrollment remains more conceptually authoritative than most IAM products; product registration/JIT must not redefine proofing. | RETAIN |
| Credential Management | Credential issuance/status is strongly supported by VC/EUDI/workload ecosystems and remains separate from presentation. | RETAIN |
| Authentication | Universally distinct product capability; sessions and authenticators reinforce separate lifecycle semantics. | RETAIN |
| Authorization | AWS, Entra, Google, Okta and ZITADEL all provide independent policy/permission/grant structures. | RETAIN |
| Identity Administration | Directly reinforced by directories, accounts, profiles, applications, provisioning and identity sources across products. | RETAIN |
| Federation | Google Workforce Identity Federation explicitly demonstrates federation without account synchronization, strongly reinforcing `Federation != Provisioning`. | RETAIN |
| Credential Exchange | Wallet/VC/EUDI-specific capability distinct from credential lifecycle and enterprise SSO. | RETAIN |
| Workload Identity | Google WIF, Microsoft Managed Identities, AWS roles and SPIFFE/SPIRE strongly reinforce a separate workload problem space. | RETAIN |
| Device Identity | Current product evidence still supports device identity as distinct from Authenticator and Workload; broader device-platform mining remains pending. | RETAIN / MORE EVIDENCE |
| Agent Identity | Emerging and not yet product-stable enough to collapse into Workload Identity; preserve as separate research-supporting subdomain pending dedicated evidence. | RETAIN / MONITOR |
| Trust Governance | EUDI/OpenID Federation/government frameworks expose registries, anchors, participation and conformity semantics that are not reducible to cryptographic trust. | RETAIN |
| Government Identity | EUDI, MOSIP and ID4D continue to justify legal/government identity as a separate supporting problem space. | RETAIN |

## Strong anti-conflation evidence from products

1. **Federation != Provisioning** — Google Workforce Identity Federation is explicitly sync-less; Keycloak and Okta also separate federation/brokering from directory synchronization.
2. **Application != ServicePrincipal** — Microsoft Entra documents a global Application object and tenant-local Service Principal objects as different representations.
3. **PermissionBundle != UFO Role** — AWS permission sets, Google roles and product roles bundle permissions operationally; they are not ontological social roles.
4. **AdministrativeDomain != IdentityContext** — AWS account/organization, Entra tenant, Okta org, Keycloak realm and ZITADEL organization are operational administration boundaries.
5. **Account linking != identity equality** — Okta and ZITADEL explicitly link federated external identities/accounts to internal user representations; this reinforces the controlled non-equality `linkedAccount` relation.
6. **Workforce Federation != Workload Federation** — Google explicitly separates workforce users from workload identities.
7. **ManagedIdentity != ServicePrincipal != Workload** — Microsoft represents managed identity through special service-principal semantics while lifecycle ownership differs between system-assigned and user-assigned forms.
8. **Session != AuthenticationResult** — mature IAM products maintain post-authentication sessions independently of authentication-event outcome artifacts.

## Result
**PASS — no DDD rename/split/merge is justified by the initial industrial benchmark.**

This is not the final Source Completeness verdict. It is an early regression result. Issue #72 must complete the wider product benchmark and Issue #66 must rerun semantic/module regression after all material-source work.

## Formalization implication
The evidence strengthens the current architecture rule that Bounded Contexts inform, but do not mechanically determine, OWL modules or microservices. The Draft PR #59 module graph remains an engineering candidate until #60/#66 pass.