# AWS Identity Ecosystem Semantic Benchmark — pass 1

Issue: #88. Evidence role: operational cloud-IAM benchmark, not ontology authority.

## Scope in pass 1
AWS IAM, IAM Identity Center, STS and Cognito identity pools, with focus on Principal, Role, policies, permission sets, account assignments, identity sources, provisioning and temporary credentials.

## High-value semantic findings

### AWS `Principal` validates the CM4DI contextual-role design
AWS policies can name users, roles, role sessions, AWS services, federated identities and accounts as principals. This strongly supports CM4DI `Principal` as a roleMixin/contextual authorization role rather than a rigid superclass.

### IAM Role is not an ontological Role
An AWS IAM Role is an assumable security identity/configuration with permissions and a trust policy. A principal assumes it, producing a **role session principal** with temporary credentials. Therefore the neutral pattern spans several CM4DI constructs:
- PermissionBundle / policy configuration;
- AccessGrant or eligibility/trust relation;
- Delegation/assumption event;
- Session;
- Principal role;
- TemporaryCredential.

Representing IAM Role as a UFO Role would be semantically incorrect.

### Role and Role Session are distinct
AWS explicitly distinguishes a role principal from a role-session principal. Once assumed, the caller uses session credentials and acts as the role session principal. This is strong operational evidence for keeping the managed authorization configuration separate from the temporal principal/session that exercises authority.

### Trust policy is access-control trust, not generic trust ontology
A role trust policy defines **who may assume the role**. Although AWS uses the word “trust,” its semantics are a policy precondition/authorization relationship. It should not be mapped to `TrustAssessment`, `TrustFramework` or `TrustChain` merely by lexical similarity.

### Effective permission is compositional and constraint-sensitive
AWS permissions are affected by identity-based policies, resource-based policies, session policies, permission boundaries and organization-level controls. This is a strong signal that a single `Permission` or `AccessGrant` object cannot encode every implementation constraint. CM4DI should preserve a neutral authorization kernel and use policy/constraint mappings plus SHACL/rules/evaluation scenarios for implementation-specific effective-permission semantics.

### IAM Identity Center exposes three distinct layers
1. **Permission Set** — a reusable template/bundle of policies.
2. **Account Assignment** — user/group + permission set + AWS account relationship.
3. **Generated IAM Role** — implementation artifact provisioned into the target account.

This strongly validates:
`PermissionBundle != AccessGrant != implementation role`.

### Identity source and federation are separate
IAM Identity Center can use a local Identity Center directory, Active Directory or an external identity provider as an identity source. SCIM provisions user/group information; SAML or other authentication federation provides SSO. This is direct evidence for:
`IdentitySource != FederationConnection != ProvisioningConnection`.

### Provisioning and deprovisioning have authorization consequences
Removing users/groups from the source and deprovisioning them is not enough if account/application assignments remain. AWS documentation explicitly treats assignment removal and identity deprovisioning as related but distinct actions. This supports an explicit lifecycle model for Account/AccessGrant rather than a single “user deleted” event.

### Cognito identity pools are federation/token-broker patterns
Cognito identity pools translate user-pool/social/OIDC/SAML authentication material into temporary AWS credentials associated with IAM roles. This supports a composite pattern involving FederationConnection, IdentityBroker, policy/claim mapping, role assumption/token exchange and TemporaryCredential.

## Relation discoveries
1. policy **names/applies to** Principal;
2. trusted principal **may assume** IAM Role;
3. AssumeRole **creates** RoleSession;
4. RoleSession **uses** TemporaryCredential;
5. Role **has** trust policy and permission policies;
6. Session policy / permission boundary **constrains** effective permission;
7. PermissionSet **is assigned to** User/Group for AWSAccount;
8. account assignment **causes provisioning of** managed IAM Role;
9. IdentitySource **supplies** users/groups to Identity Center;
10. SCIM provisioning **synchronizes** source users/groups into target store;
11. GroupMembership **causes inheritance/availability of** group account assignments;
12. Cognito identity pool **brokers** external identity material to STS credentials.

## Lifecycle and constraint discoveries
- IAM user credential lifecycle;
- role creation/trust-policy/permission-policy update/deletion;
- role assumption session creation/expiration;
- temporary credential issuance/expiration;
- permission set create/update/provision/deprovision;
- account assignment create/remove;
- user/group provisioning/deprovisioning;
- group membership changes driving effective access;
- identity-source migration can invalidate prior assignments;
- explicit deny and policy intersections constrain effective access.

## Candidate semantic deltas to test in #66
1. **AccessGrant lifecycle/status** may need explicit treatment.
2. generic **assumption/activation of authority** event may be useful beyond AWS, especially for role/session and JIT access systems.
3. a generic **PolicyConstraint** or formal constraint allocation may be needed, but this likely belongs outside Core and may be handled via AccessPolicy/AccessCondition + SHACL/rule semantics.
4. `TemporaryCredential` currently lives in Workload Identity but AWS demonstrates human/federated use too; ownership/module placement should be rechecked without necessarily changing the concept.
5. source migration/assignment survival is a useful CQ for Identity Administration.

## DDD verdict
No Domain rename is justified. AWS strongly reinforces separate Authorization, Identity Administration, Federation and Workload Identity problem spaces. `AWS Account` is an implementation administrative/resource boundary and should not be promoted to `IdentityContext`.

## New discovery opportunities
- **Role Activation / Assumption Pattern** benchmark across AWS STS, Entra PIM/role assignment, Google service-account impersonation and PAM/JIT products.
- **Effective Permission Composition** benchmark across AWS policies, Entra Conditional Access/RBAC, Google IAM Conditions, XACML/AuthZEN and Cerbos/OpenFGA.
- **Identity Source Migration** lifecycle scenarios across AWS, Okta and other directory platforms.
- **Human and workload temporary credential unification** analysis for module ownership.

## Remaining before closing #88
IAM Roles Anywhere; service-linked roles; IAM user/group details; organization/SCP semantics; Cognito user pools versus identity pools; Identity Center application assignments; exact APIs/data models; CQ mappings; final #66 disposition.
