# Gemara Skills

A [Lola](https://github.com/RedHatProductSecurity/lola) module that provides AI skills for creating and validating [Gemara](https://github.com/gemaraproj/gemara) security artifacts.

## What's Included

### Skills

| Skill | Description |
|-------|-------------|
| **threat-assessment** | Step-by-step wizard for creating a Gemara-compatible Threat Catalog (Layer 2) |
| **control-catalog** | Step-by-step wizard for creating a Gemara-compatible Control Catalog (Layer 2) |

### Commands

| Command | Description |
|---------|-------------|
| `/validate-artifact <file>` | Validate a Gemara artifact YAML file against its CUE schema |

### MCP Server

The module configures the [gemara-mcp](https://github.com/gemaraproj/gemara-mcp) server via Docker, providing the `validate_gemara_artifact` tool for CUE schema validation.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/) (for the gemara-mcp server)
- [Lola](https://github.com/RedHatProductSecurity/lola) (`uv tool install git+https://github.com/RedHatProductSecurity/lola`)

## Installation

### Register the module

```bash
lola mod add https://github.com/gemaraproj/gemara-skills.git
```

### Install to your project

```bash
# Install for Cursor
lola install gemara-skills -a cursor

# Install for Claude Code
lola install gemara-skills -a claude-code

# Install for Gemini CLI
lola install gemara-skills -a gemini-cli

# Install for OpenCode
lola install gemara-skills -a opencode
```

### Declarative install via `.lola-req`

Add to your project's `.lola-req` file:

```
gemara-skills
```

Then run:

```bash
lola sync
```

## What Gets Installed

| Assistant | Skills | Commands | MCP Config |
|-----------|--------|----------|------------|
| Cursor | `.cursor/skills/threat-assessment/`, `.cursor/skills/control-catalog/` | `.cursor/commands/validate-artifact.md` | `.cursor/mcp.json` |
| Claude Code | `.claude/skills/threat-assessment/`, `.claude/skills/control-catalog/` | `.claude/commands/validate-artifact.md` | `.mcp.json` |
| Gemini CLI | `GEMINI.md` (managed section) | `.gemini/commands/validate-artifact.toml` | `.gemini/settings.json` |
| OpenCode | `AGENTS.md` (managed section) | `.opencode/commands/validate-artifact.md` | OpenCode MCP config |

## Usage

Once installed, the skills are automatically discovered by your AI assistant. Ask it to:

- "Create a threat catalog for my API gateway"
- "Help me build a control catalog for our container runtime"
- Use `/validate-artifact controls.yaml` to validate an existing artifact

The assistant will walk you through the process step-by-step, using the `validate_gemara_artifact` tool to verify your artifacts against the Gemara CUE schema.

## License

Apache-2.0
