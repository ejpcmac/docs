# Tech stack overview

| Scope           | Element                  | Decision                                                                                 | ADR |
| --------------- | ------------------------ | ---------------------------------------------------------------------------------------- | --- |
| Conventions     | ADR template             | [MADR]                                                                                   |     |
| Conventions     | Versioning               | [Semantic Versioning]                                                                    |     |
| Conventions     | Changelog                | [Keep a Changelog]                                                                       |     |
| Conventions     | Commits                  | [Conventional Commits]                                                                   |     |
| Conventions     | Git branching            | [Git Flow with extensions]                                                               |     |
| Tools           | Version control          | [Git]                                                                                    |     |
| Tools           | Toolchain management     | [Nix] + [direnv]                                                                         |     |
| Tools           | Commit helper            | [git-z]                                                                                  |     |
| Tools           | Commit linter            | [committed]                                                                              |     |
| Documentation   | Platform                 | Text files tracked by [Git]                                                              |     |
| Documentation   | Markup language          | [GitHub Flavored Markdown]                                                               |     |
| Documentation   | Diagrams                 | [Mermaid]                                                                                |     |
| Blogging        | Platform                 | Static site                                                                              |     |
| Blogging        | Site generator           | [Zola]                                                                                   |     |
| Configuration   | Language                 | [TOML] (default)<br>[YAML] (complex cases)                                               |     |
| Dev/CLI         | Language                 | [Rust]                                                                                   |     |
| Dev/CLI         | Argument parsing         | [clap]                                                                                   |     |
| Dev/CLI         | Prompt                   | [inquire]                                                                                |     |
| Dev/CLI         | CLI tests                | [rexpect]<br>[assert_cmd]<br>[assert_fs]                                                 |     |
| Dev/Embedded    | Language                 | [Rust]                                                                                   |     |
| Dev/Embedded    | Concurrency framework    | [RTIC]                                                                                   |     |
| Dev/Embedded    | Log / tracing            | [defmt]                                                                                  |     |
| Dev/Embedded    | Serialisation format     | [postcard]                                                                               |     |
| Dev/GUI         | Language                 | [Rust]                                                                                   |     |
| Dev/GUI         | Framework                | [relm4] (to be revised)                                                                  |     |
| Dev/Web         | Back-end framework       | [Ash] + [Phoenix] ([Elixir])                                                             |     |
| Dev/Web         | Front-end framework      | [Phoenix LiveView] ([Elixir])                                                            |     |
| Lang/Nix        | Flake management         | [flake-parts]                                                                            |     |
| Lang/Nix        | Devshell                 | [devshell]                                                                               |     |
| Lang/Nix        | Rust toolchain           | [rust-overlay]                                                                           |     |
| Lang/Nix        | Rust packaging           | [naersk]                                                                                 |     |
| Lang/Nix        | Formatter                | [nixpkgs-fmt] (to be revised)                                                            |     |
| Lang/Rust (std) | Error management         | [thiserror] (lib)<br>[eyre] (app)                                                        |     |
| Lang/Rust (std) | Log / tracing            | [tracing]                                                                                |     |
| Lang/Rust (std) | ORM                      | [Diesel]                                                                                 |     |
| Lang/Rust (std) | Templating               | [askama] (static)<br>[tera] (dynamic)                                                    |     |
| Lang/Rust (std) | Ordered maps             | [indexmap]                                                                               |     |
| Lang/Rust (std) | Test runner              | [cargo-nextest]                                                                          |     |
| Lang/TOML       | Formatter                | [taplo]                                                                                  |     |
| Lang/YAML       | Formatter                | [prettier]                                                                               |     |
| Lang/JSON       | Formatter                | [prettier]                                                                               |     |
| Office          | Task management          | [Org Mode]                                                                               |     |
| Office          | Note taking              | [Org Mode]                                                                               |     |
| Office          | Mailer                   | [mu4e]                                                                                   |     |
| Office          | Messaging client         | [Element] ([Matrix])                                                                     |     |
| Office          | Word processing          | [Pandoc Markdown] + [Pandoc] with [LaTeX] backend (general)<br>[LaTeX] (letters, resume) |     |
| Office          | Presentation             | [Pandoc Markdown] + [Pandoc] with [Beamer] ([LaTeX]) backend                             |     |
| Office          | Spreadsheet              | [LibreOffice Calc]                                                                       |     |
| Infra/Desktop   | Operating system         | [NixOS]                                                                                  |     |
| Infra/Desktop   | File system              | [ZFS]                                                                                    |     |
| Infra/Desktop   | Configuration management | [NixOS]                                                                                  |     |
| Infra/Desktop   | Dotfile management       | [home-manager] ([Nix])                                                                   |     |
| Infra/Desktop   | Shell                    | [Zsh] + [Oh My Zsh]                                                                      |     |
| Infra/Desktop   | Desktop environment      | [bspwm] + [sxhkd] + [Polybar]                                                            |     |
| Infra/Desktop   | Launcher                 | [Rofi]                                                                                   |     |
| Infra/Desktop   | Terminal emulator        | [Termite]                                                                                |     |
| Infra/Desktop   | Terminal multiplexer     | [Tmux]                                                                                   |     |
| Infra/Desktop   | File manager             | [ranger] (main)<br>[PCManFM] (for thumbnails)                                            |     |
| Infra/Desktop   | Text editor              | [Spacemacs]                                                                              |     |
| Infra/Desktop   | Web browser              | [Firefox]                                                                                |     |
| Infra/Desktop   | Code editor              | [VSCodium]                                                                               |     |
| Infra/Desktop   | Backup                   | [ZFS snapshots] (local)<br>[syncoid] ([ZFS] replication)<br>[rsync] (other replication)  |     |
| Infra/Server    | Operating system         | [NixOS]                                                                                  |     |
| Infra/Server    | Configuration management | [NixOS]                                                                                  |     |
| Infra/Server    | File system              | [ZFS]                                                                                    |     |
| Infra/Server    | Shell                    | [Zsh] + [Oh My Zsh]                                                                      |     |
| Infra/Server    | Terminal multiplexer     | [Tmux]                                                                                   |     |
| Infra/Server    | File manager             | [ranger]                                                                                 |     |
| Infra/Server    | Text editor              | [Vim]                                                                                    |     |
| Infra/Server    | Backup                   | [ZFS snapshots] (local)<br>[syncoid] ([ZFS] replication)                                 |     |
| Infra/Server    | Container platform       | [NixOS Containers]                                                                       |     |
| Infra/Server    | Log database             | [Elasticsearch] (to be revised)                                                          |     |
| Infra/Server    | Database                 | [PostgreSQL]                                                                             |     |
| Infra/Server    | Mail server              | [NixOS Mailserver] (Postfix + Dovecot + OpenDKIM + rspamd)                               |     |
| Infra/Server    | Web server               | [Apache HTTP Server]                                                                     |     |
| Infra/Server    | Messaging server         | [Synapse] ([Matrix])                                                                     |     |
| Infra/Server    | Git forge                | [GitLab] (self-hosted)<br>[GitHub] (public projects)                                     |     |
| Infra/Server    | Home cloud               | [Nextcloud]                                                                              |     |

[Apache HTTP Server]: https://httpd.apache.org/
[Ash]: https://www.ash-hq.org/
[Beamer]: https://ctan.org/pkg/beamer
[Conventional Commits]: https://www.conventionalcommits.org/en/v1.0.0/
[Diesel]: https://diesel.rs/
[Elasticsearch]: https://www.elastic.co/elasticsearch
[Element]: https://element.io/
[Elixir]: https://elixir-lang.org/
[Firefox]: https://www.mozilla.org/firefox/new/
[Git Flow with extensions]: https://ejpcmac.net/blog/about-my-git-workflow/#naming-and-flow
[GitHub Flavored Markdown]: https://github.github.com/gfm/
[GitHub]: https://github.com/
[GitLab]: https://about.gitlab.com/
[Git]: https://git-scm.com/
[Keep a Changelog]: https://keepachangelog.com/en/1.1.0/
[LaTeX]: https://www.latex-project.org/
[LibreOffice Calc]: https://www.libreoffice.org/discover/calc/
[MADR]: https://adr.github.io/madr/
[Matrix]: https://matrix.org/
[Mermaid]: https://mermaid.js.org/
[Nextcloud]: https://nextcloud.com/
[NixOS Containers]: https://wiki.nixos.org/wiki/NixOS_Containers
[NixOS Mailserver]: https://gitlab.com/simple-nixos-mailserver/nixos-mailserver
[NixOS]: https://nixos.org/
[Nix]: https://nixos.org/
[Oh My Zsh]: https://ohmyz.sh/
[Org Mode]: https://orgmode.org/
[PCManFM]: https://github.com/lxde/pcmanfm
[Pandoc Markdown]: https://pandoc.org/MANUAL.html#pandocs-markdown
[Pandoc]: https://pandoc.org/
[Phoenix LiveView]: https://hexdocs.pm/phoenix_live_view/welcome.html
[Phoenix]: https://phoenixframework.org/
[Polybar]: https://github.com/polybar/polybar
[PostgreSQL]: https://www.postgresql.org/
[RTIC]: https://rtic.rs/2/book/en/
[Rofi]: https://github.com/davatorium/rofi
[Rust]: https://www.rust-lang.org/
[Semantic Versioning]: https://semver.org/
[Spacemacs]: https://www.spacemacs.org/
[Synapse]: https://github.com/element-hq/synapse
[TOML]: https://toml.io/
[Termite]: https://github.com/thestinger/termite
[Tmux]: https://github.com/tmux/tmux/wiki
[VSCodium]: https://vscodium.com/
[Vim]: https://www.vim.org/
[YAML]: https://yaml.org/
[ZFS snapshots]: https://illumos.org/books/zfs-admin/snapshots.html#gbciq
[ZFS]: https://openzfs.org/
[Zola]: https://www.getzola.org/
[Zsh]: https://zsh.org/
[askama]: https://github.com/rinja-rs/askama
[assert_cmd]: https://github.com/assert-rs/assert_cmd
[assert_fs]: https://github.com/assert-rs/assert_cmd
[bspwm]: https://github.com/baskerville/bspwm
[bépo]: https://bepo.fr/wiki/Accueil
[cargo-nextest]: https://nexte.st/
[clap]: https://github.com/clap-rs/clap
[committed]: https://github.com/crate-ci/committed
[defmt]: https://github.com/knurling-rs/defmt
[devshell]: https://github.com/numtide/devshell
[direnv]: https://direnv.net/
[eyre]: https://github.com/eyre-rs/eyre
[flake-parts]: https://github.com/hercules-ci/flake-parts
[git-z]: https://github.com/ejpcmac/git-z
[home-manager]: https://github.com/nix-community/home-manager
[indexmap]: https://github.com/indexmap-rs/indexmap
[inquire]: https://github.com/mikaelmello/inquire
[mu4e]: https://github.com/djcb/mu
[naersk]: https://github.com/nix-community/naersk
[nixpkgs-fmt]: https://github.com/nix-community/nixpkgs-fmt
[postcard]: https://github.com/jamesmunns/postcard
[prettier]: https://prettier.io/
[ranger]: https://ranger.fm/
[relm4]: https://relm4.org/
[rexpect]: https://github.com/rust-cli/rexpect
[rsync]: https://rsync.samba.org/
[rust-overlay]: https://github.com/oxalica/rust-overlay
[sxhkd]: https://github.com/baskerville/sxhkd
[syncoid]: https://github.com/jimsalterjrs/sanoid?tab=readme-ov-file#syncoid
[taplo]: https://taplo.tamasfe.dev/
[tera]: https://github.com/Keats/tera
[thiserror]: https://github.com/dtolnay/thiserror
[tracing]: https://github.com/tokio-rs/tracing