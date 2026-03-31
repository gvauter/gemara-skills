# Gemara Security Framework

Gemara is a layered security model framework for defining, evaluating, and enforcing security controls. Artifacts are YAML documents validated against CUE schemas published in the `github.com/gemaraproj/gemara` module.

## Available Skills

| Skill | Use When |
|-------|----------|
| `threat-assessment` | Creating a new Threat Catalog (Layer 2) for a component or technology |
| `control-catalog` | Creating a new Control Catalog (Layer 2) with controls, families, and assessment requirements |

When the user asks to create a security artifact, check if a skill matches and load it.

## Available Tool

The `validate_gemara_artifact` tool is provided by the gemara-mcp server (configured in `mcps.json`). Use it to validate YAML artifacts against Gemara CUE schema definitions:

- `#ControlCatalog` -- Control catalogs with families, controls, and assessment requirements
- `#ThreatCatalog` -- Threat catalogs with capabilities and threats
- `#GuidanceCatalog` -- Guidance catalogs (Layer 1)
- `#Policy` -- Policies (Layer 3)
- `#EvaluationLog` -- Evaluation logs (Layer 5)

## Available Command

- `/validate-artifact <file-path>` -- Quickly validate a Gemara artifact file against its schema

## Schema Documentation

Read the `gemara://schema/definitions` MCP resource for field-level CUE schema definitions. Use `gemara://lexicon` for term definitions.

## Resources

- Schema docs: https://gemara.openssf.org/schema/layer-2.html
- Gemara project: https://github.com/gemaraproj/gemara
