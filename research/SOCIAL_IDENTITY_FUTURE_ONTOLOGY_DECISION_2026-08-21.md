# Social Identity Future-Ontology Opportunity Decision

## Decision
**YES — the evidence supports a future independent Social Identity Ontology research track, but NOT an expansion of CM4DI Core.**

The future work should be aligned with UFO and connected to CM4DI through explicit bridge mappings where technical digital-identity artifacts represent, assert, disclose or authenticate socially meaningful identity information.

## Why an independent ontology is justified
The evidence shows a coherent construct family with distinct theories, relations and phenomena that are only partially representable by IAM-oriented identity models:
- social identity and social identification;
- self-categorization and group/collective identity;
- social and role identity;
- group membership and affiliation;
- self-identification and attributed identity;
- persona, self-presentation and self-disclosure;
- reputation and social perception;
- identity salience, strength and commitment;
- social relationships, audience and context collapse;
- group norms and social/institutional context.

This is not merely a list of attributes. It is a domain with its own ontological questions about agents, collective agents, roles, social relators, qualities, perceptions, normative descriptions, membership, self-concept and context.

## Recommended scientific framing
A future project should be framed as a **UFO-grounded reference ontology of social identity and identity-in-social-context**, not as a social-media ontology and not as an extension of IAM.

Possible research questions:
1. What foundational distinctions are required to represent personal, role-based, group-based and collective social identities without conflating actor, role, membership, self-concept and attributed perception?
2. How should self-identified, socially attributed and institutionally recognized identities be distinguished and related?
3. How can persona, self-presentation, reputation and social perception be modeled across online and offline contexts?
4. How should social identity connect to technical digital identity artifacts without reducing either domain to the other?

## Provisional modules
1. **Actor and Collective Core** — Person, SocialAgent, CollectiveAgent, Group/Organization.
2. **Membership and Affiliation** — Membership, Affiliation, Belonging, duration/context.
3. **Role and Role-Identity** — SocialRole, RolePlaying, RoleIdentity, normative/institutional definition.
4. **Identification and Self-Concept** — SocialIdentification, SelfCategorization, IdentitySalience/Strength/Commitment.
5. **Attribution and Perception** — SelfIdentification, AttributedIdentity, SocialPerception, reputation.
6. **Presentation and Persona** — Persona, SelfPresentation, SelfDisclosure, Audience.
7. **Context and Relationship** — SocialContext, SocialRelationship, ContextCollapse, norms.
8. **Digital Bridge** — links to CM4DI DigitalIdentity, Account/Profile, Claim, Credential, IdentityAttribute and federation artifacts.

## Reuse policy
Do not reinvent established semantics when existing ontologies are adequate:
- UFO for SocialAgent, SocialRole, NormativeDescription, SocialRelator and commitments;
- W3C ORG for Organization/Membership/Role publication patterns;
- SDHSS Social Life Core as a comparative/reference ontology for membership, social relationship, social perception and social role;
- CM4DI only for technical digital-identity bridge concepts.

## Explicit non-decision
This Issue does **not** create the future ontology repository, article, OWL or OntoUML model. The current project only records the opportunity and boundary so CM4DI journal-v2 remains focused.

## CM4DI policy resulting from this decision
- Social login stays inside Enterprise/Federation Profile as an authentication/federation use case.
- Social identity constructs remain outside Core.
- Social facts may be represented as Claim/Attribute content without importing the full social ontology.
- `Social-Future` remains a valid Issue #9 disposition.
- Any future bridge must preserve non-equivalence between technical representation and social/psychological identity.
