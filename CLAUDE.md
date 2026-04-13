# CLAUDE.md

## Overview

This repository contains the core catalog for the [FINOS Common Cloud Controls](https://commoncloudcontrols.com) project. It defines the foundational controls, threats, and capabilities that are shared across all service-specific catalogs. Files conform to the Gemara schema.

## Gemara MCP Server

This repo includes a `.mcp.json` that configures the Gemara MCP server. Use it to **validate catalog files** against the schema during editing:

- `validate_gemara_artifact` — validate a YAML file against the Gemara schema
- `migrate_gemara_artifact` — migrate a file to a newer schema version
- `gemara://schema/definitions` — browse the schema type definitions
- `gemara://lexicon` — look up Gemara terminology

**Always validate after making changes** to catalog files.

## Files

- `controls.yaml` — core controls (CCC.Core.CN01–CN20)
- `threats.yaml` — core threats (CCC.Core.TH01–TH25)
- `capabilities.yaml` — core capabilities (CCC.Core.CP01–CP31)
- `metadata.yaml` — catalog metadata (mapping references for CCM, MITRE ATT&CK)

## Entry IDs

- Controls: `CCC.Core.CN<nn>`
- Threats: `CCC.Core.TH<nn>`
- Capabilities: `CCC.Core.CP<nn>`

## Groups

Every entry must have a `group:` field. The group describes what security or operational domain the entry belongs to.

| Group ID | Use When The Entry Is About... |
|---|---|
| `Encryption` | Cryptographic protection — encryption, key management, certificates |
| `Access` | Authentication, authorization, trust perimeters, least privilege |
| `Observability` | Logging, metrics, alerting, audit trail integrity |
| `Data` | Replication, backup, recovery, data retention, region restrictions |
| `Resource` | Resource lifecycle, scaling, cost management, tagging |
| `Compute` | CPU, memory, storage allocation, runtime, execution |
| `Ingestion` | Active/passive data ingestion, input validation |
| `Networking` | Network infrastructure, traffic management |
| `Orchestration` | Workload coordination, CI/CD, job scheduling |
| `Processing` | ETL, data transformation, lineage |
| `Messaging` | Pub/sub, message delivery, ordering |
| `MachineLearning` | ML environments, model registries, inference |

**Decision rule:** Ask "what breaks if this is missing / what goes wrong if this materializes?" and pick the group that matches.

## Reference IDs in Mappings

Parent `reference-id` in mapping sections must be fully qualified:
- In `threat-mappings`: use `CCC.Core.Threats`
- In `capabilities`: use `CCC.Core.Capabilities`
- Never use bare `CCC`
