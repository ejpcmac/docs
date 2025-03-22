<!--
SPDX-FileCopyrightText: 2025 Jean-Philippe Cugnet <jean-philippe@cugnet.eu>
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# Commit Guidelines

## Commit content

A commit should contain an atomic change.

An atomic change is the minimal set of changes that goes from a consistent state
A to another consistent state B.

### Examples

#### New feature

When adding a new interface to a module, the commit may contain the addition of
several types and function that would not exist without each other.

#### Refactoring

When changing an interface that is used by other modules in the same project,
the commit should contain both the update to the interface itself, and the
integration of the change in modules using it. Not doing the second part would
lead to an inconsistent state.

#### New feature with prior refactoring

When adding a new feature, some refactoring of the existing code may be needed
to allow its integration. In this case, the refactoring work should be included
in one or more separate commits before the one introducing the feature. This
greatly enhances the readability of the history, and eases the review process.

## Commit message

* Conventional Commits 1.0.0
* type list (with examples)
* scope list
* description lowercas, no dot, imperative
* Ref footer with ticket (optional)
* examples
