# CCC Core Catalog

This repository contains the core catalog for the [FINOS Common Cloud Controls](https://www.finos.org/common-cloud-controls-project) project — a set of reusable capabilities, threats, and controls that apply broadly across cloud service types.

Rather than duplicating common entries in every service-specific catalog, this catalog acts as a shared reference point. Service catalogs import from it by ID, keeping definitions consistent and centrally version-controlled.

## Contents

| File | Description |
|---|---|
| `capabilities.yaml` | Platform-level capabilities common to all cloud services |
| `threats.yaml` | Threats applicable regardless of service type |
| `controls.yaml` | Controls that address those cross-cutting threats |
| `metadata.yaml` | Supplementary catalog metadata |

## How other catalogs use this

Service catalogs in [capability-catalogs](https://github.com/common-cloud-controls/capability-catalogs), [threat-catalogs](https://github.com/common-cloud-controls/threat-catalogs), and [control-catalogs](https://github.com/common-cloud-controls/control-catalogs) reference entries from this catalog by ID under the `imports` key. See [CONTRIBUTING.md](CONTRIBUTING.md) for the full schema and examples.

## Delivery

At release time, the [CCC delivery toolkit](https://github.com/finos/common-cloud-controls/tree/main/delivery-toolkit) ingests these files and produces versioned Markdown artifacts for publication.

## License

[Community Specification License 1.0](LICENSE)
