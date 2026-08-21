# CM4DI Journal V2 — Social Identity Boundary and Overlap Matrix

## Scope rule
This artifact separates **social login** (an IAM/federation mechanism) from **social identity** (a psychosocial/sociological construct family). No lexical similarity is sufficient for ontology merging.

## Primary boundary
Recent transdisciplinary digital-identity research explicitly distinguishes system-oriented digital identity from online identity/social selfhood. Social Digital Identity Theory (2026) further shows that online and offline group memberships, identity salience and platform affordances shape social-digital selfhood. These findings justify an adjacent research lane, not expansion of CM4DI Core into psychology/sociology.

## Boundary matrix

| Construct | Meaning in social-identity research | Closest CM4DI construct | Merge? | Decision |
|---|---|---|---|---|
| Social Identity | group/socially grounded part of self-concept | DigitalIdentity / IdentitySubject | **No** | `SOCIAL-FUTURE`; explicit exclusion from Core |
| Social Login | authentication using external social platform IdP | Federation / Authentication / IdP / RP | Yes, as IAM mapping only | Enterprise/Federation Profile |
| Social Identification | process/degree of identifying with group | none | No | Social-Future |
| Self-Categorization | seeing self as member of a social category/group | none | No | Social-Future |
| Group/Collective Identity | shared/group-based identity and meaning | Party/Organization/IdentitySubject | No | Social-Future; avoid equating group identity with digital record of a group |
| Membership | relation between agent and group/organization | Claim/Attribute content; possible Party relation | Not Core duplication | Reference W3C ORG / future bridge |
| Affiliation | social/organizational association | IdentityAttribute / Claim content | Not Core duplication | Profile mapping / external reference |
| Social Role | role defined/recognized in a social/institutional context | IdP/RP/Verifier/etc. interaction roles | No lexical merge | UFO grounding / explicit alignment |
| Role Identity | self-meaning attached to occupying a role | none | No | Social-Future |
| Persona | curated/performative presentation of self | Account/Profile candidate | No | Social-Future; anti-conflation with technical Profile |
| Self-Presentation | process of presenting a selected self to audiences | Claim/Presentation events | No | Social-Future with possible bridge |
| Self-Disclosure | social act of revealing self-information | credential/attribute disclosure | No | Social-Future; technical disclosure remains profile-specific |
| Self-Identification | self-ascription of an identity/category | Claim provenance | No direct merge | Future bridge through provenance |
| Attributed Identity | identity assigned/perceived by others | Claim / Attribute / verifier evidence | No direct merge | Future bridge through attribution provenance |
| Reputation | aggregated evaluation by others | Trust / TrustAssessment | No | Social-Future; reputation is not generic trust |
| Social Perception | how an actor is interpreted by others | Claim/Trust overlap | No | Social-Future |
| Identity Salience | contextual prominence of an identity | IdentityContext | No | Social-Future; IdentityContext is not a psychological salience measure |
| Identity Strength | intensity of identification | none | No | Social-Future |
| Identity Commitment | attachment to a role/group identity | UFO commitment / IAM obligation | No | Social-Future; collision warning |
| Social Relationship | friendship/kinship/community relation | generic Party relations | No | Social-Future |
| Audience | people/groups for whom self is presented | IdentityContext | No | Social-Future; possible context bridge |
| Context Collapse | multiple social contexts/audiences collapsing online | IdentityContext | No | Social-Future; explicit non-equivalence |
| Group Norm | norm influencing group behavior/identity | Policy / NormativeDescription | No direct merge | Foundational/external alignment |

## Anti-conflation rules
1. `SocialIdentity ≠ DigitalIdentity`.
2. `SocialLogin ≠ SocialIdentity`.
3. `RoleIdentity ≠ SocialRole ≠ IAM Role ≠ interaction role`.
4. `Persona ≠ Account/Profile ≠ DigitalIdentity`.
5. `Reputation ≠ Trust ≠ Assurance`.
6. `GroupMembership ≠ GroupIdentification`.
7. `IdentitySalience ≠ IdentityContext`.
8. `SelfDisclosure ≠ CredentialPresentation`.
9. `AttributedIdentity ≠ verified IdentityAttribute`.
10. `CollectiveIdentity ≠ Organization/Group digital identity record`.
11. `GroupNorm ≠ access-control Policy`.
12. `ContextCollapse ≠ multiple technical identity contexts`.

## Reuse/linking policy
- Use UFO social-role/social-agent semantics where foundational grounding is needed rather than recreating them in CM4DI.
- Use W3C ORG as a mapping/reference for organization membership, affiliation and role-in-organization when needed by example/profile data.
- Treat SDHSS Social Life Core as an adjacent ontology/reference for future social-life modeling, not an import into CM4DI Core.
- Social claims (e.g., affiliation) may appear as **content** of CM4DI Claims/Attributes without making the full social construct a CM4DI Core class.

## Gate-B implication
Issue #9 should preserve `Social-Future` as a separate disposition category. The social-identity candidate family should not enter Core unless a very specific cross-stream requirement independently demands a neutral primitive; even then, the primitive must be defined without importing psychological/social-theory semantics into digital identity management.
