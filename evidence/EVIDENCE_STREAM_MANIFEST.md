# Evidence Stream Manifest

This manifest prevents evidence-ID collisions while discovery streams execute independently before Issue #9 normalization.

| Stream | Registry | Allocated evidence IDs | Status | Central merge |
|---|---|---|---|---|
| Normative standards / protocols | `EVIDENCE_REGISTRY.csv` | `CM4DI-EVID0001`–`CM4DI-EVID0029` | Reviewed | Already central |
| Government / trust frameworks | `government/GOVERNMENT_EVIDENCE_REGISTRY.csv` | `CM4DI-EVID0030`–`CM4DI-EVID0045` | Reviewed | Pending Issue #9 |
| Enterprise / cloud IAM / SSO | `enterprise/ENTERPRISE_IAM_EVIDENCE_REGISTRY.csv` | `CM4DI-EVID0046`–`CM4DI-EVID0070` | Reviewed | Pending Issue #9 |
| Machine / workload / device / AI-agent identity | `nonhuman/NONHUMAN_IDENTITY_EVIDENCE_REGISTRY.csv` | `CM4DI-EVID0071`–`CM4DI-EVID0090` | Reviewed | Pending Issue #9 |
| Reference implementations / conformance / datasets | `implementations/IMPLEMENTATION_DATA_EVIDENCE_REGISTRY.csv` | `CM4DI-EVID0091`–`CM4DI-EVID0105` | Reviewed | Pending Issue #9 |
| Academic literature / competitor models | `academic/ACADEMIC_EVIDENCE_REGISTRY.csv` | `CM4DI-EVID0106`–`CM4DI-EVID0120` | Reviewed | Pending Issue #9 |

## Allocation rule
New discovery streams must continue after the highest reserved evidence ID and record their range here before creating evidence records. Issue #9 will deduplicate, normalize supersession/status, and merge curated records into the central registry without renumbering retained evidence IDs.
