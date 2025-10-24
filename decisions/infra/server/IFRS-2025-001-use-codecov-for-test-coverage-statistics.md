---
status: "accepted"
created: 2025-10-12
updated: 2025-10-12
decision-makers: Jean-Philippe Cugnet
consulted: N/A
informed: N/A
---

<!--
SPDX-FileCopyrightText: 2025 Jean-Philippe Cugnet <jean-philippe@cugnet.eu>
SPDX-License-Identifier: CC-BY-SA-4.0
-->

# Use Codecov for test coverage statistics on public projects

## Context and Problem Statement

I want to display the test coverage information for my projects in continuous
integration, and track historical data. My public projects are hosted on GitHub
([IFRS-YYYY-XXX]), which does not provide a way to achieve so. Third-party
services are however available. Which one should I use?

## Decision Drivers

* Is free for open source projects
* Is simple to configure
* Provides diffs between builds
* Shows a diff in pull requests
* Has a dark theme
* Can export historical data

## Considered Options

* [Codecov](https://web.archive.org/web/20251006181410/https://about.codecov.io/)
* [Coveralls](https://web.archive.org/web/20251011171504/https://coveralls.io/)

## Decision Outcome

Chosen option: Codecov, because it is both more readable and seems to have more
interesting features than Coveralls.

## Pros and Cons of the Options

### Codecov

* Good, because it is free for open source projects
* Good, because there is an easy-to-follow tutorial
* Good, because it provides diffs between builds
* Good, because it can post a message in pull requests with diff info
* Good, because it has a dark theme
* Good, because it lets you define components to split coverage results
* Bad, because it cannot export historical data

### Coveralls

* Good, because it is free for open source projects
* Good, because it can comment on PRs with the impact on coverage
* Good, because it provides diffs between builds
* Good, because it can post a message in pull requests with diff info
* Good, because it can block PRs on coverage limits
* Neutral, because the configuration is simple but documentation is not super
    clear
* Bad, because it does not have a dark theme
* Bad, because their interface is a bit noisy and lacks contrasts
* Bad, because it cannot export historical data

## More Information

If at some point GitHub natively supports code coverage, avoiding the use of a
third-party tool should be strongly considered.

[IFRS-YYYY-XXX]: ../../placeholder.md
