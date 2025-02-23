---
status: accepted
date: 2025-02-22
decision-makers: Jean-Philippe Cugnet
consulted: N/A
informed: N/A
---

# Use MADR 4.0 for recording decisions

## Context and Problem Statement

I want to record technical decisions made on my projects and infrastructure so
they can be reused across projects and shared with others. Which format should
these records follow?

## Decision Drivers

* Is Markdown files ([DOC-2016-002]) tracked by Git ([DOC-2016-001])
* Structured by using sections
* Easy to write
* Easy to read
* Possible to record decisions not related to software development
* Records the rationale behind the decision
* Allows to record pros and cons of the options so I can remember why I have
    chosen the given option over others

## Considered Options

* [MADR](https://adr.github.io/madr/) 4.0
* [Michael Nygard’s template](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions)
* [EdgeX Foundry ADR
  template](https://github.com/joelparkerhenderson/architecture-decision-record/tree/fa8810756586e6d69ff4e41b93cee4c4a4480e07/locales/en/templates/decision-record-template-by-edgex)
* [Decision record template by Jeff Tyree and Art
  Akerman](https://github.com/joelparkerhenderson/architecture-decision-record/tree/fa8810756586e6d69ff4e41b93cee4c4a4480e07/locales/en/templates/decision-record-template-by-jeff-tyree-and-art-akerman)

## Decision Outcome

Chosen option: MADR 4.0, because:

* it is the only one to fit all my requirements,
* it is flexible with optional sections,
* it is simple to write and read.

## Pros and Cons of the Options

### MADR

* Good, because it provides templates for Markdown files.
* Good, because it is structured.
* Good, because some sections are optional to make it easy to write.
* Good, because section ordering is [optimised for easy
    readability](https://adr.github.io/madr/decisions/0016-outcome-before-detailed-pros-cons.html).
* Good, because it clearly records the rationale in the “Decision Outcome”
    section.
* Good, because it has an optional “Pros and Cons of the Options” section.
* Good, because it is possible to record the consequences.
* Neutral, because it has an optional “Decisions Drivers” section that
    formalises the decision requirements.
* Neutral, because metadata is captured in a YAML front matter.

### Mychael Nygard’s template

* Good, because it is structured.
* Good, because there are few sections, making it easy to read and write.
* Neutral, because it can record the rationale in the “Decision” section.
* Neutral, because there is a mandatory “Consequences” section which may not
    always be useful.
* Neutral, because the status is under a section.
* Bad, because there is no section for pros and cons of the options.

### EdgeX Foundry ADR template

* Good, because it provides templates for Markdown files.
* Good, because it is structured.
* Neutral, because there is a “Change Log” section which seems duplicating the
  use of Git.
* Neutral, because metadata is in a section.
* Bad, because it needs a reference use case in addition to the context.
* Bad, because it needs a justification of why an ADR is even needed.
* Bad, because it is tailored for software architecture only.
* Bad, because there is no section for pros and cons of the options.

### Decision record template by Jeff Tyree and Art Akerman

* Good, because it has a “Notes” section that allows to add more information
    about the decision process.
* Neutral, because it is structured as a list of items.
* Bad, because there is no explicit section for pros and cons of the options.
* Bad, because there are too many sections that can make writing an ADR overly
    complicated for simple matters.

[DOC-2016-001]: ../placeholder.md
[DOC-2016-002]: ../placeholder.md
