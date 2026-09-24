# Layouni and Pollet vs CM4DI — Preliminary Comparison

Owner: #101 / #136  
Status: **Preliminary; full OWL/class/property extraction remains required.**

The 2009 work explicitly presents an OWL ontology for federated identity management. It is therefore a direct historical formal-ontology comparator, especially for CM4DI's Federation, Identity Administration and Trust Governance contexts.

Current comparison:
- Both use machine-readable ontology artifacts, but CM4DI adds UFO/OntoUML conceptual grounding before OWL projection.
- The 2009 scope is federation-centric; CM4DI separates `Federation`, `FederationConnection`, `IdentityBroker`, `RelyingParty`, `Authentication`, `Session`, `Provisioning` and governance/trust constructs.
- CM4DI must demonstrate that its federation model is not a repackaging of earlier IdP/SP/circle-of-trust ontologies, but a broader cross-paradigm integration layer.
- Full comparison must inspect intermediate concepts, OWL axioms, reasoning and implementation/evaluation evidence.

No novelty claim is frozen before that extraction.
