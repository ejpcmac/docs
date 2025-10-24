---
status: accepted
created: 2025-03-19
updated: 2025-03-19
decision-makers: Jean-Philippe Cugnet
consulted: N/A
informed: N/A
---

<!--
SPDX-FileCopyrightText: 2025 Jean-Philippe Cugnet <jean-philippe@cugnet.eu>
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# Add created / updated dates to the ADR template

## Context and Problem Statement

I am using MADR 4.0 for recording decisions ([CO-2025-001]). This template
defines an optional YAML front matter that contains a `date` field, documented
as the date *when the decisions was last updated*.

However, it is good to keep the information about when the decision was
initially taken. How should I record that?

## Considered Options

* Stick to MADR 4.0, updating the date when changing the status or adding new
    information.
* Stick to MADR 4.0, but do not update the date when updating the status or
    adding new information.
* Replace `date` with `created` / `updated` fields.

## Decision Outcome

Chosen option: “Replace `date` with `created` / `updated` fields”, because this
is what gives the more clarity about the current status and the accuracy of the
information.

[CO-2025-001]: ./CO-2025-001-use-madr-4.0-for-recording-decisions.md
