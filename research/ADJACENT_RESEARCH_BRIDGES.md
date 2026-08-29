# CM4DI Adjacent Research Bridges

## Purpose

CM4DI is the digital-identity reference-ontology Research (`R-015`). Related Researches may consume or provide semantics through explicit bridge mappings, but they do not become CM4DI modules solely because they are adjacent.

## R-031 SemSocialIdentity

**Boundary:** Social Identity is a separate Research object.

SemSocialIdentity is intended to cover, after its own evidence and conceptual gates, social-identity phenomena such as self-identification, attributed identity, social role, affiliation, collective identity, persona, reputation, identity salience and social context.

CM4DI remains authoritative for DigitalIdentity, Identifier, Account/UserProfile as system representations, proofing, credentials, authentication, authorization, federation, trust governance, government identity and non-human digital identity.

### Anti-conflation

- `SocialIdentity != DigitalIdentity`
- `SocialLogin != SocialIdentity`
- `Account != SocialIdentity`
- `UserProfile != SocialIdentity`
- `Persona != Account`
- `Reputation != Identity`

### Bridge direction

Candidate bridge patterns include DigitalIdentity as a representation locus for social-identity expression, Account as a platform locus for persona expression, Claim as a possible assertion of attributed identity, and IdentityContext as potentially overlapping with SocialContext. None is a formal equivalence.

SemSocialIdentity is currently a private governed-bootstrap repository. CM4DI public navigation must not depend on access to it.

## R-003 Commentium

Commentium owns comment/discourse semantics: Comment events, Commenter roles, message/interpretation structures, interaction contexts, intent, stance and related discourse constructs.

CM4DI may provide digital-identity context for agents/accounts/authentication; SemSocialIdentity may later provide persona/reputation/social-role context. Neither adjacent ontology absorbs Commentium's discourse Core.

Public repository: https://github.com/ArazSaieArasi3/Commentium

## R-004 Newsium

Newsium owns news/information semantics, including its eventual actor/source/document/event structures after its own evidence gates.

CM4DI may provide digital-identity semantics for actors/accounts/identifiers where relevant; SemSocialIdentity may later provide affiliation/persona/reputation/social-identity context. Neither bridge changes Newsium's semantic ownership.

Public repository: https://github.com/ArazSaieArasi3/Newsium

## Governance

1. Cross-research bridge rows must name source Research, target Research, semantic intent and ownership.
2. `owl:sameAs`, `owl:equivalentClass` and `owl:equivalentProperty` require explicit formal evidence and review.
3. Shared foundational semantics should align through UFO/gUFO or another justified neighbor ontology rather than be duplicated independently.
4. Bridge changes must be regression-tested against each affected Research's competency questions and ownership boundaries.
5. Public landing pages may describe private Research relationships but must not require private-repository access for essential navigation.
