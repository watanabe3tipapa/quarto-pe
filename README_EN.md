# quarto-pe

**Quarto, systematized.**

quarto-pe is a cheat-sheet / reference site that gathers Quarto's **`_quarto.yml` notation** and **Q markdown syntax** into one place. It systematically documents only real keys based on official specs, and ships copy-paste templates, live examples, and real-world case studies.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-v0.4.0-blue.svg)](https://github.com/watanabe3tipapa/quarto-pe/releases)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-live-blue.svg)](https://watanabe3tipapa.github.io/quarto-pe/)
[![GitHub](https://img.shields.io/github/issues/watanabe3tipapa/quarto-pe.svg)](https://github.com/watanabe3tipapa/quarto-pe/issues)

[日本語](README.md) | [English](README_EN.md)

## Concept

### Why "pe"

Quarto is powerful, but its `_quarto.yml` keys are scattered across `project` / `format` / `website` / `book` / `execute`, and online information is polluted with non-existent syntax and incorrect commands.

quarto-pe "**curates it as a personal edition**" — systematically collecting only real keys and real commands based on official specs. Instead of jumping between unreliable sources, you reach the correct answer in one place.

| Activity | quarto-pe counterpart |
|---|---|
| Look up configuration keys | [_quarto.yml reference](https://watanabe3tipapa.github.io/quarto-pe/reference.html) organizes `project` / `format` / `website` / `book` / `execute` / `vars` |
| Learn how to write the body | [Q markdown notation](https://watanabe3tipapa.github.io/quarto-pe/notation.html) covers headings, Div, callouts, cross-refs, math, and variables with live samples |
| Prepare an initial config | Copy-paste a setup from the [config templates](https://watanabe3tipapa.github.io/quarto-pe/content3.html) |
| Try dynamic content | [Code execution & dynamic content](https://watanabe3tipapa.github.io/quarto-pe/content4.html) demos R chunks, parameters, and Observable JS |
| Finish with structure & multi-format | Apply cross-refs, callouts, layout, and bibliography via [structure & multi-format](https://watanabe3tipapa.github.io/quarto-pe/content5.html) |
| Learn real-world practices | See [real-site YAML](https://watanabe3tipapa.github.io/quarto-pe/content2.html) and [this site's config](https://watanabe3tipapa.github.io/quarto-pe/content1.html) |
| Publish | Automatic GitHub Pages deployment via GitHub Actions |

### Accuracy Comes First

This site only covers **real, existing keys and commands**. The non-existent syntax included in early versions (`defaults` key, `output-extensions`, `quarto check project`, `lang: jp`, etc.) has been fully corrected. Every key is verified to actually work with Quarto 1.3+ before being published.

- **Systematized** — real keys organized by category (old errors fully removed)
- **Live examples** — code chunks, Observable JS, and cross-references run in place
- **Copy-paste ready** — templates you can paste straight into your project

## Features

- **Systematized reference**: all `_quarto.yml` keys classified into `project` / `format` / `website` / `book` / `execute` / `vars`
- **Q markdown notation**: headings, Div, callouts, cross-refs, math, variables, and shortcodes with live samples
- **Live examples**: R code chunks, inline code, and Observable JS executed in place
- **Template collection**: 15 sections of config templates (project / output formats / website / blog / book, etc.)
- **Case studies**: this site's own config and real-site YAML dissected
- **Accuracy**: only real keys based on official specs (old errors fully corrected)
- **CI auto-publish**: GitHub Actions runs `quarto render` and auto-deploys `_site/` to GitHub Pages

## Installation

### Prerequisites

| Tool | Required version | Check command |
|---|---|---|
| [Quarto](https://quarto.org/docs/get-started/) | >= 1.3 | `quarto --version` |
| R | optional (only if running R chunks) | `R --version` |
| Git | optional (deploy / contribution) | `git --version` |

On macOS install Quarto with `brew install quarto`. Install R from https://cran.r-project.org.

### 1. Get the repository

```bash
git clone https://github.com/watanabe3tipapa/quarto-pe.git
cd quarto-pe
```

### 2. Preview

```bash
quarto preview
```

### 3. Render

```bash
quarto render
```

Output goes to `_site/`. To render a single file, use e.g. `quarto render reference.qmd`.

### 4. Publish

Pushing to `main` triggers an automatic build and deploy via GitHub Actions.

## Contents

| Page | Description |
|---|---|
| [index.qmd](index.qmd) | Landing page |
| [reference.qmd](reference.qmd) | `_quarto.yml` notation reference |
| [notation.qmd](notation.qmd) | Q markdown notation reference |
| [content1.qmd](content1.qmd) | This site's config (case study) |
| [content2.qmd](content2.qmd) | Real-site YAML case studies |
| [content3.qmd](content3.qmd) | `_quarto.yml` template collection |
| [content4.qmd](content4.qmd) | Code execution & dynamic content templates |
| [content5.qmd](content5.qmd) | Structure & multi-format templates |

For newcomers, start with the [reference](https://watanabe3tipapa.github.io/quarto-pe/reference.html) for the basics, then browse the [template collection](https://watanabe3tipapa.github.io/quarto-pe/content3.html).

## Documentation

- [_quarto.yml reference](https://watanabe3tipapa.github.io/quarto-pe/reference.html) — all project config keys
- [Q markdown notation](https://watanabe3tipapa.github.io/quarto-pe/notation.html) — how to write the body
- [Template collection](https://watanabe3tipapa.github.io/quarto-pe/content3.html) — practical templates

Development notes are in [DEV-MEMO](DEV-MEMO.md), changes in [CHANGELOG](CHANGELOG.md).

## Contributing

Contributions are welcome. This site's policy is "**only real keys, and accurately**". If you find an error or an inaccurate description, please open an [issue](https://github.com/watanabe3tipapa/quarto-pe/issues) to share it first.

1. Fork the repository
2. Create a feature branch (`git checkout -b fix/typo-in-reference`)
3. Commit your changes (`git commit -m 'Fix typo in reference'`)
4. Push to the branch (`git push origin fix/typo-in-reference`)
5. Open a Pull Request

## Contact

GitHub: [https://github.com/watanabe3tipapa/quarto-pe](https://github.com/watanabe3tipapa/quarto-pe)

Published site: [https://watanabe3tipapa.github.io/quarto-pe/](https://watanabe3tipapa.github.io/quarto-pe/)

## License

Distributed under the MIT License — see the [LICENSE](LICENSE) file for details.
