---
status: accepted
created: 2025-10-24
updated: 2025-10-24
decision-makers: Jean-Philippe Cugnet
consulted: N/A
informed: N/A
---

# Follow REUSE for tracking licensing information

## Context and Problem Statement

I am writing open source software. I share this software with other people, and
others can also contribute to it. I want to make it clear who owns the copyright
on which (part of a) file, and under what license a file is licensed. How should
I proceed?

## Decision drivers

* Is specified / standard
* Is machine-readable
* Is machine-enforceable
* Supports multiple licenses in the same repository
* Supports multiple licenses in the same file (bonus)

## Considered Options

* Follow the [REUSE] specification
* Put a `LICENSE` file in the repository and appropriate copyright headers

## Decision Outcome

Chosen option: “Follow the REUSE specification”, because it gives a clear frame
on how to add precise information in every file and comes with tooling.

## Confirmation

`reuse lint` should be called in CI scripts whenever applicable.

[REUSE]: https://reuse.software/
