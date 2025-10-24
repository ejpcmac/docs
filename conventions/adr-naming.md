<!--
SPDX-FileCopyrightText: 2025 Jean-Philippe Cugnet <jean-philippe@cugnet.eu>
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# ADR Naming

## General rule

Decisions are stored in files named like:

    category/CAT-YYYY-NNN-title-with-dashes.md

where:

* `category` is a subfolder for the category in lowercase,
* `CAT` is the category identifier in uppercase,
* `YYYY` is the year of the decision,
* `NNN` is a sequential number, reset every year and local to the category,
* `title-with-dash` is the short name of the decision in kebab case.

This decision can be referred unambiguously as `CAT-YYYY-NNN`.

## Categories

| Category      | Subfolder       | Identifier |
| ------------- | --------------- | ---------- |
| Conventions   | `conventions`   | `CO`       |
| Tools         | `tools`         | `T`        |
| Documentation | `documentation` | `DOC`      |
| Blogging      | `blogging`      | `BLOG`     |
| Configuration | `configuration` | `CFG`      |
| Dev/CLI       | `dev/cli`       | `CLI`      |
| Dev/Embedded  | `dev/embedded`  | `EMB`      |
| Dev/GUI       | `dev/gui`       | `GUI`      |
| Dev/Web       | `dev/web`       | `WEB`      |
| Lang/C        | `lang/c`        | `C`        |
| Lang/Nix      | `lang/nix`      | `NIX`      |
| Lang/Python   | `lang/python`   | `PY`       |
| Lang/Rust     | `lang/rust`     | `RUST`     |
| Lang/TOML     | `lang/toml`     | `TOML`     |
| Lang/YAML     | `lang/yaml`     | `YAML`     |
| Lang/JSON     | `lang/json`     | `JSON`     |
| Office        | `office`        | `OE`       |
| Infra/Desktop | `infra/desktop` | `IFRD`     |
| Infra/Server  | `infra/server`  | `IFRS`     |
