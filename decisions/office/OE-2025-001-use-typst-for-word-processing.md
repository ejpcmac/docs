---
status: accepted
created: 2025-03-01
updated: 2025-03-01
decision-makers: Jean-Philippe Cugnet
consulted: N/A
informed: N/A
---

<!--
SPDX-FileCopyrightText: 2025 Jean-Philippe Cugnet <jean-philippe@cugnet.eu>
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# Use Typst for word processing

## Context and Problem Statement

I sometimes need to write documents that can be printed or shared as a PDF.

In [OE-2019-001], I decided to use [Pandoc Markdown] + [Pandoc] with the [LaTeX]
backend for general documents because it combines the simple interface of
Markdown with the powerful document generation of LaTeX. However, I also decided
to stick with bare [LaTeX] for documents with a very specific format (letters
and CV), because Pandoc Markdown is not flexible enough for all cases.

Since then, [Typst] has appeared as an interesting contender. Should I revise my
choice?

## Decision Drivers

* Output quality
* Simplicity
* Flexibility

## Considered Options

* Keep using [Pandoc Markdown] + [Pandoc] with the [LaTex] backend or [LaTeX],
    depending on the document
* Switch to [Typst] for all documents

## Decision Outcome

Chosen option: “Switch to Typst for all documents”, because:

* the quality of the output is comparable to LaTeX,
* it is much simpler to use Typst than combining Pandoc with LaTeX,
* Typst has a simple syntax, comparable to Markdown for basic markup,
* Typst is as flexible as LaTeX in term of document layout, and maybe more since
    its embedded programming language is much simpler to write.

[LaTeX]: https://www.latex-project.org/
[OE-2019-001]: ../placeholder.md
[Pandoc Markdown]: https://pandoc.org/MANUAL.html#pandocs-markdown
[Pandoc]: https://pandoc.org/
[Typst]: https://typst.app/
