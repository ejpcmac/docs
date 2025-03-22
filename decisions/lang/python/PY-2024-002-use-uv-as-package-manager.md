---
status: accepted
created: 2024-10-29
updated: 2024-10-29
decision-makers: Jean-Philippe Cugnet
consulted: N/A
informed: N/A
---

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

* uv follows [PEP-621] for project definition,
* uv puts the virtual environment in a `.venv` directory inside the project,
    which is more standard than what Poetry does,
* uv is way faster than Poetry,
* uv can also select the proper Python version to use in the project if a
    `.python-version` file is present, which is not supported by Poetry,
* there are no features of Poetry I am using that are not supported by uv,
* it is easy to build a Nix package from a uv project by using [uv2nix], from
    the same author as [poetry2nix],
* uv has already ~24000 stars on GitHub only 8 months after its initial
    publication, gaining traction very quickly.
* uv is maintained by Astral, which also maintains Ruff.

### Consequences

* Good, because uv follows Python standards more than Poetry.
* Good, because uv is way faster than Poetry.
* Good, because uv can also handle the Python version.
* Bad, because it means migrating projects from Poetry to uv.

[Hatch]: https://hatch.pypa.io/latest/
[PDM]: https://pdm-project.org/en/latest/
[PEP-621]: https://peps.python.org/pep-0621/
[PY-2023-001]: ./PY-2023-001-use-poetry-as-package-manager.md
[Poetry]: https://python-poetry.org/
[conda]: https://docs.conda.io/en/latest/
[pip]: https://pip.pypa.io/en/stable/
[poetry2nix]: https://github.com/nix-community/poetry2nix
[uv2nix]: https://github.com/pyproject-nix/uv2nix
[uv]: https://docs.astral.sh/uv/
