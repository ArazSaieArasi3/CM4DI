# Evidence Stream Manifest

This manifest governs evidence-ID allocation and the Gate-B normalization state. Stream-specific registries remain the authoritative detailed provenance records; Gate-B synthesis normalizes them without renumbering retained evidence IDs.

| Stream | Registry | Allocated evidence IDs | Status | Gate-B normalization |
|---|---|---|---|---|
| Normative standards / protocols | `EVIDENCE_REGISTRY.csv` | `CM4DI-EVID0001`–`CM4DI-EVID0029` | Reviewed | Included in Gate-B synthesis |
| Government / trust frameworks | `government/GOVERNMENT_EVIDENCE_REGISTRY.csv` | `CM4DI-EVID0030`–`CM4DI-EVID0045` | Reviewed | Included in Gate-B synthesis |
| Enterprise / cloud IAM / SSO | `enterprise/ENTERPRISE_IAM_EVIDENCE_REGISTRY.csv` | `CM4DI-EVID0046`–`CM4DI-EVID0070` | Reviewed | Included in Gate-B synthesis |
| Machine / workload / device / AI-agent identity | `nonhuman/NONHUMAN_IDENTITY_EVIDENCE_REGISTRY.csv` | `CM4DI-EVID0071`–`CM4DI-EVID0090` | Reviewed | Included in Gate-B synthesis |
| Reference implementations / conformance / datasets | `implementations/IMPLEMENTATION_DATA_EVIDENCE_REGISTRY.csv` | `CM4DI-EVID0091`–`CM4DI-EVID0105` | Reviewed | Included in Gate-B synthesis |
| Academic literature / competitor models | `academic/ACADEMIC_EVIDENCE_REGISTRY.csv` | `CM4DI-EVID0106`–`CM4DI-EVID0120` | Reviewed | Included in Gate-B synthesis |
| Social-identity opportunity / boundary | `social/SOCIAL_IDENTITY_EVIDENCE_REGISTRY.csv` | `CM4DI-EVID0121`–`CM4DI-EVID0134` | Reviewed / segregated | Included with default disposition `Social-Future` unless explicitly bridged |

## Gate-B totals
- Retained evidence IDs: **134**.
- Evidence ranges are contiguous from `CM4DI-EVID0001` through `CM4DI-EVID0134`.
- Detailed records remain in their stream registries because schemas capture stream-specific provenance and semantic fields more faithfully than a lossy flattened union.
- Cross-stream deduplication, version/status control and evidence grading are documented in `synthesis/EVIDENCE_NORMALIZATION_AND_GRADING.md`.
- Candidate-level normalization and Gate-B dispositions are documented in `synthesis/NORMALIZED_CONCEPT_DECISION_REGISTER.csv`.

## Allocation rule after Gate B
New evidence must continue after `CM4DI-EVID0134`; existing IDs are immutable and are never reused or renumbered. If a source is superseded, preserve its ID and record the successor rather than replacing provenance history.
