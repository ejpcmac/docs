---
status: superseded by PY-2024-002
created: 2023-04-12
updated: 2024-10-29
decision-makers: Jean-Philippe Cugnet
consulted: N/A
informed: N/A
---

# Use Poetry as package manager

*This ADR is superseded by [PY-2024-002].*

## Context and Problem Statement

Python does not come with a built-in modern project and package management
system like those we can find in Rust (cargo), Elixir (Mix + Hex) and JavaScript
(npm). However, the community has built several tools enhancing the situation.
Which of them should I use?

## Decision Drivers

* Handles project definition (package name, version, …)
* Specifies dependencies in semver format to enable compatible updates
* Has a lock file
* Isolates dependencies between projects
* Can build a wheel
* Is compatible with Nix
* Is widely adopted

## Considered Options

* [pip](https://web.archive.org/web/20230410171117/https://pip.pypa.io/en/stable/)
* [conda](https://web.archive.org/web/20230412213124/https://docs.conda.io/projects/conda/en/stable/)
* [Hatch](https://web.archive.org/web/20230327031014/https://hatch.pypa.io/latest/)
* [Poetry](https://web.archive.org/web/20230407160742/https://python-poetry.org/)
* [PDM](https://web.archive.org/web/20240406050206/https://pdm-project.org/en/latest/)

## Decision Outcome

Chosen option: Poetry, because:

* like PDM, it provides a full-featured cargo-like experience, with:
    * project definition,
    * locked, semver-updatable dependencies,
    * automated virtual environment management,
    * an integrated build system;
* it seems to have a community 6 times bigger than PDM,
* support for automated Nix packaging is better, with `poetry2nix`.

### Consequences

* Good, because this brings modern project and package management to Python
    projects.
* Good, because there is no need anymore to manually handle virtual
    environments.
* Good, because it enables easy Nix packaging.
* Bad, because it means installing one more tool for contributors.
* Bad, because it does not perfectly follow Python standards (the project and
  dependency definitions use a tool-specific format instead of [PEP-621]).

## Pros and Cons of the Options

### pip

* Good, because it is bundled with Python and standard.
* Good, because versions can be specified in a semver-compatible format.
* Neutral, because dependencies can be specified in a `requirements.txt`.
* Neutral, because a Nix package can be build using [pip2nix].
* Bad, because it does not handle project definition.
* Bad, because versions are not locked.
* Bad, because it is possible to install dependencies without writing them into
    a file.
* Bad, because by default the dependencies are not isolated between projects.
* Bad, because it does not include a build system for wheels.

### conda

* Good, because it performs a true dependency resolution.
* Neutral, because an environment can be specified in an `environment.yml`.
* Bad, because it does not handle project definition.
* Bad, because versions are not locked by default.
* Bad, because metadata is specified in a non-standard way.
* Bad, because the conda environment is not tied to a specific project.
* Bad, because it does not include a build system for wheels.
* Bad, because it is only adopted in the data science community, so less
    widespread than other alternatives.

### Hatch

* Good, because it handles project definition in the `pyproject.toml`.
* Good, because the project definition is in the `project` table as defined by
    [PEP-621].
* Good, because versions can be specified in a semver-compatible format.
* Good, because it automatically manages virtual environments per project.
* Good, because it can build a wheel through the `hatch build` command.
* Good, because it strictly follows the Python standards.
* Neutral, because it has ~3800 stars on GitHub.
* Bad, because versions are not locked.

### Poetry

* Good, because it handles project definition in the `pyproject.toml`.
* Good, because versions can be specified in a semver-compatible format.
* Good, because dependencies are locked in a `Poetry.lock` file.
* Good, because it automatically manages a virtual environment per project.
* Good, because it can build a wheel through the `poetry build` command.
* Good, because a Nix package can be build using [poetry2nix], which uses the
    `Poetry.lock`.
* Good, because it has ~24000 stars on GitHub.
* Neutral, because the project definition is tool-specific, under the
    `tool.poetry` table.

### PDM

* Good, because it handles project definition in the `pyproject.toml`.
* Good, because the project definition is in the `project` table as defined by
    [PEP-621].
* Good, because versions can be specified in a semver-compatible format.
* Good, because dependencies are locked in a `pdm.lock` file.
* Good, because it automatically manages a virtual environment per project.
* Good, because it supports [PEP-582] for local dependencies instead of virtual
    environments.
* Good, because it can build a wheel through the `pdm build` command.
* Neutral, because it has ~4000 stars on GitHub.
* Bad, because while a Nix package can be created by [pdm2nix], it seems quite
    niche (17 stars only).

[PY-2024-002]: ./PY-2024-002-use-uv-as-package-manager.md
[PEP-582]: https://peps.python.org/pep-0582/
[PEP-621]: https://peps.python.org/pep-0621/
[pdm2nix]: https://github.com/adisbladis/pdm2nix
[pip2nix]: https://github.com/nix-community/pip2nix
[poetry2nix]: https://github.com/nix-community/poetry2nix
