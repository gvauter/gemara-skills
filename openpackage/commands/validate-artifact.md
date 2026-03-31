---
description: Validate a Gemara artifact YAML file against its CUE schema
argument-hint: <file-path>
---

Read the file at `$1` and determine the artifact type from the `metadata.type` field.

Map the type to its CUE definition:

| `metadata.type` | Definition |
|------------------|------------|
| ControlCatalog | `#ControlCatalog` |
| ThreatCatalog | `#ThreatCatalog` |
| GuidanceCatalog | `#GuidanceCatalog` |
| Policy | `#Policy` |
| EvaluationLog | `#EvaluationLog` |

Call `validate_gemara_artifact` with the file contents and the matching definition.

Present results in a table:

| Field | Result |
|-------|--------|
| File | $1 |
| Schema | {definition used} |
| Valid | true/false |
| Message | {message from tool} |
| Errors | {count, or "None"} |

If errors exist, list each error and suggest fixes.
