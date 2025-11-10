---
status: accepted
created: 2024-10-29
updated: 2025-03-22
decision-makers: Jean-Philippe Cugnet
consulted: N/A
informed: N/A
---

<!--
SPDX-FileCopyrightText: 2025 Jean-Philippe Cugnet <jean-philippe@cugnet.eu>
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# Use uv as package manager

## Context and Problem Statement

Python does not come with a built-in modern project and package management
system like those we can find in Rust (cargo), Elixir (Mix + Hex) and JavaScript
(npm). However, the community has built several tools enhancing the situation.

In [PY-2023-001], I decided to use [Poetry] to handle this task, choosing it
over [pip], [conda], [Hatch] and [PDM]. Since then, [uv] has appeared as an
interesting contender. Should I revise my choice?

## Considered Options

* Keep using [Poetry]
* Switch to [uv]

## Decision Outcome

Chosen option: “Switch to uv”, because:

* uv follows [PEP-621] for project definition[^1],
* uv puts the virtual environment in a `.venv` directory inside the project,
    which is more standard than what Poetry does,
* uv is way faster than Poetry,
* uv can also select the proper Python version to use in the project if a
    `.python-version` file is present, which is not supported by Poetry,
* there are no features of Poetry I am using that are not supported by uv,
* it is easy to build a Nix package from a uv project by using [uv2nix], from
    the same author as [poetry2nix] [^2],
* uv has already ~24000 stars on GitHub only 8 months after its initial
    publication, gaining traction very quickly.
* uv is maintained by Astral, which also maintains Ruff.

### Consequences

* Good, because uv follows Python standards more than Poetry.
* Good, because uv is way faster than Poetry.
* Good, because uv can also handle the Python version.
* Bad, because it means migrating projects from Poetry to uv.

[^1]: 2025-03-22: Poetry 2.0, released on 2025-01-05, now supports PEP-621 as
    well.
[^2]: 2025-03-22: poetry2nix [is not maintained
    anymore](https://github.com/nix-community/poetry2nix/commit/f554d27c1544d9c56e5f1f8e2b8aff399803674e)
    since 2024-11-10.

[Hatch]: https://web.archive.org/web/20241012043931/https://hatch.pypa.io/latest/
[PDM]: https://web.archive.org/web/20241020201250/https://pdm-project.org/en/latest/
[PEP-621]: https://peps.python.org/pep-0621/
[PY-2023-001]: ./PY-2023-001-use-poetry-as-package-manager.md
[Poetry]: https://web.archive.org/web/20241024173404/https://python-poetry.org/
[conda]: https://web.archive.org/web/20241016152250/https://docs.conda.io/en/latest/
[pip]: https://web.archive.org/web/20241024171148/https://pip.pypa.io/en/stable/
[poetry2nix]: https://github.com/nix-community/poetry2nix
[uv2nix]: https://github.com/pyproject-nix/uv2nix
[uv]: https://web.archive.org/web/20241013190024/https://docs.astral.sh/uv/
