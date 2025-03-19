---
status: accepted
created: 2025-02-23
updated: 2025-02-23
decision-makers: Jean-Philippe Cugnet
consulted: N/A
informed: N/A
---

# Use custom naming for ADRs

## Context and Problem Statement

I want to record past and future decisions made on my projects and
infrastructure in a Git repository. The template format is defined to follow
MADR 4.0 in [CO-2025-001]. Given that the decisions can apply to a broad range
of categories, how should the files be named and organised?

## Decision Drivers

* Possible to refer unambiguously to a decision
* Possible to record decisions retroactively while keeping a quasi-chronological
    ordering
* Possible to list the decisions for a given category

## Considered Options

* [MADR-0005] – No subfolders with global sequential IDs
* [MADR-0010] – Subfolders with local sequential IDs
* Category identifier in filename and per-category sequential ID
* Category identifier in filename and per-category yearly sequential ID
* [Custom naming] – Subfolders with category identifier in filename and
    per-category yearly sequential ID

## Decision Outcome

Chosen option: [Custom naming] (subfolders with category identifier in filename
and per-category yearly sequential ID), because it is the only option fitting
all the requirements without adding a bad consequence.

## Pros and Cons of the Options

### No subfolders with global sequential IDs

    NNNN-title-with-dashes.md

#### Examples

* `decisions/0032-use-git-for-version-control.md`
* `decisions/0141-use-custom-naming-for-adrs.md`

#### Pros / Cons

* Good, because it is possible to refer unambiguously to a decision (e.g.
    `ADR-0141`).
* Neutral, because it is a no brainer to create a new file.
* Bad, because it is not possible to list the decitions for a given category.
* Bad, because retroactively added decisions could have a later sequence ID than
    more recent decisions.

### Subfolders with local sequential IDs

    category/NNNN-title-with-dashes.md

#### Examples

* `decisions/conventions/0008-use-custom-naming-for-adrs.md`
* `decisions/tools/0001-use-git-for-version-control.md`

#### Pros / Cons

* Good, because it is straightforward to list decisions for a given category.
* Neutral, because a contributor has to know to which category belongs the
    decision.
* Bad, because it is not possible to refer unambiguously to a decision.
* Bad, because retroactively added decisions could have a later sequence ID than
    more recent decisions.

### Category identifier in filename and per-category sequential ID

    CAT-NNNN-title-with-dashes.md

#### Examples

* `decisions/CO-0008-use-custom-naming-for-adrs.md`
* `decisions/T-0001-use-git-for-version-control.md`

#### Pros / Cons

* Good, because it is possible to refer unambiguously to a decision (e.g.
    `CO-0008`).
* Good, because it is possible to list decisions for a given category by
    filtering.
* Neutral, because a contributor has to know to which category belongs the
    decision.
* Bad, because category identifiers can be obscure to newcomers.
* Bad, because retroactively added decisions could have a later sequence ID than
    more recent decisions.

### Category identifier in filename and per-category yearly sequential ID

    CAT-YYYY-NNN-title-with-dashes.md

#### Examples

* `decisions/CO-2025-002-use-custom-naming-for-adrs.md`
* `decisions/T-2015-001-use-git-for-version-control.md`

#### Pros / Cons

* Good, because it is possible to refer unambiguously to a decision (e.g.
    `CO-2025-002`).
* Good, because it is possible to record decisions from previous years while
    keeping a quasi-chronological ordering.
* Good, because it is possible to list decisions for a given category by
    filtering.
* Neutral, because a contributor has to know to which category belongs the
    decision.
* Bad, because category identifiers can be obscure to newcomers.

### Subfolders with category identifier in filename and per-category yearly sequential ID

    category/CAT-YYYY-NNN-title-with-dashes.md

#### Examples

* `decisions/conventions/CO-2025-002-use-custom-naming-for-adrs.md`
* `decisions/tools/T-2015-001-use-git-for-version-control.md`

#### Pros / Cons

* Good, because it is possible to refer unambiguously to a decision (e.g.
    `CO-2025-002`).
* Good, because it is possible to record decisions from previous years while
    keeping a quasi-chronological ordering.
* Good, because it is straightforward to list decisions for a given category.
* Neutral, because a contributor has to know to which category belongs the
    decision.
* Neutral, because category identifiers can be inferred from other files in the
    same subfolder.

## More information

In a new project where past decisions do not exist, using a purely sequential
naming would likely be the best option. A naming scheme could be derived from
the [Custom naming] to remove the year information while still benefitting from
the unambiguous identifiers.

If the project is reduced in scope, it would be even better to stick to
[MADR-0005] in order to provide the simplest developer experience possible.

[Custom naming]: ../../conventions/adr-naming.md
[CO-2025-001]: ./CO-2025-001-use-madr-4.0-for-recording-decisions.md
[DOC-2016-001]: ../placeholder.md
[MADR-0005]: https://adr.github.io/madr/decisions/0005-use-dashes-in-filenames.html
[MADR-0010]: https://adr.github.io/madr/decisions/0010-support-categories.html
