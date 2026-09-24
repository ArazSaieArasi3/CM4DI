# semDIM vs CM4DI — Preliminary Comparison

Owner: #103 / #136  
Status: **Preliminary; full-text axiom extraction remains required.**

## Confirmed source-level characteristics
semDIM is a semantic distributed identity-management approach for persons, groups and roles across namespaces. The public abstract states that it uses `owl:sameAs` as a central property for representing and verifying distributed identities through formal reasoning.

## High-value comparison
- **Identity equality:** semDIM's explicit `owl:sameAs` strategy contrasts with CM4DI's conservative separation of `IdentitySubject`, `DigitalIdentity`, `Account` and `linkedAccount`.
- **Scope:** semDIM focuses on distributed semantic identity across social/professional networks; CM4DI targets cross-paradigm digital-identity semantics spanning enterprise IAM, federation, credentials, government, workload/device/agent identity and trust governance.
- **Groups and roles:** semDIM group/role constructs require careful comparison with CM4DI `AccessGroup`, `GroupMembership`, contextual roles and the external SemSocialIdentity boundary; no lexical equivalence is assumed.
- **Formal reasoning:** semDIM is a useful reasoning comparator. CM4DI must demonstrate why its more conservative co-reference policy avoids invalid global identity collapse while remaining queryable.

## Current CM4DI implication
No Core delta is accepted yet. The main candidate contribution is an explicit equality/co-reference policy and test suite contrasting `linkedAccount` with `owl:sameAs`.

## Remaining
Full-text extraction of ontology modules, DUL patterns, axioms, reasoning tasks, evaluation and implementation architecture.
