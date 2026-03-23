# Gemara Skills (OpenPackage)

An [OpenPackage](https://openpackage.dev/) package that provides AI skills for creating and validating [Gemara](https://github.com/gemaraproj/gemara) security artifacts.

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

The package configures the [gemara-mcp](https://github.com/gemaraproj/gemara-mcp) server via Docker, providing the `validate_gemara_artifact` tool for CUE schema validation.

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/) (for the gemara-mcp server)
- [OpenPackage CLI](https://openpackage.dev/docs) (`npm install -g opkg`)

## Installation

```bash
# From the repo
opkg install gh@gvauter/gemara-skills

# Or from a local clone
opkg install ./opkg

# Install to specific platforms
opkg install gh@gvauter/gemara-skills --platforms cursor claude
```

## Usage

Once installed, the skills are automatically discovered by your AI assistant. Ask it to:

- "Create a threat catalog for my API gateway"
- "Help me build a control catalog for our container runtime"
- Use `/validate-artifact controls.yaml` to validate an existing artifact

The assistant will walk you through the process step-by-step, using the `validate_gemara_artifact` tool to verify your artifacts against the Gemara CUE schema.

## License

Apache-2.0
