# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- Landing page (`index.qmd`) as a portal to all contents
- `_quarto.yml` notation reference (`reference.qmd`, replacing `_quarto-yml-reference.md`)
- Expanded Q markdown notation reference (`notation.qmd`)
- Neo-brutalism theme (`theme.scss`)
- English README (`README_EN.md`)

### Changed

- `_quarto.yml`: output-dir moved to `_site`, HTML-only formats, corrected `resources`/`freeze` placement, `lang: ja`
- Fixed incorrect reference content (removed `defaults`, `output-extensions`, `quarto check project`, `quarto config`, etc.)
- Standardized front matter across content pages (Japanese descriptions, `lang: ja`, no per-page CSS/PDF)
- README simplified (Japanese primary)
- CI: install knitr only, removed TinyTeX, uploads `./_site`
- Display-only code blocks now use the official double-brace (`{{r}}`) + 4-backtick pattern instead of `{verbatim}` (which does not work in Quarto 1.3.x)
- Inline-code examples use `<code>` tags so knitr does not evaluate them inside fenced blocks
- Variable shortcodes escaped with triple braces (`{{{< var >}}}`) to avoid `Unknown var` warnings
- Removed `format.pdf` from `signin.qmd` / `content1.qmd` (PDF no longer rendered)

### Removed

- Tracked build artifacts and R caches (`docs/`, `notation_cache/`, `notation_files/`, `.Rproj.user/`, `.Rhistory`)
- `custom-styles.css` (merged into `styles.css`)
- CNAME/.nojekyll custom-domain claims (not in use)

[Unreleased]: https://github.com/watanabe3tipapa/quarto-pe/compare/HEAD...HEAD
