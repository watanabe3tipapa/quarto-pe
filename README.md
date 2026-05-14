<!-- badges -->
[![License](https://img.shields.io/github/license/watanabe3tipapa/quarto-pe.svg)](LICENSE)
[![Stars](https://img.shields.io/github/stars/watanabe3tipapa/quarto-pe.svg)](https://github.com/watanabe3tipapa/quarto-pe/stargazers)
[![Last commit](https://img.shields.io/github/last-commit/watanabe3tipapa/quarto-pe/main.svg)](https://github.com/watanabe3tipapa/quarto-pe/commits/main)
[![PRs welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Maintenance](https://img.shields.io/badge/Maintenance-Active-brightgreen.svg)](https://github.com/watanabe3tipapa/quarto-pe)
[![Changelog](https://img.shields.io/badge/Changelog-Keep%20a%20Changelog-green.svg)](CHANGELOG.md)

[English](README.md) | [日本語](README_ja.md)

# quarto-pe

Personal reference project for **Quarto `_quarto.yml` notation** and **Q markdown syntax**.

This repository serves as a memo/cheat sheet for Quarto project configuration — covering `project`, `format`, `defaults`, `book`, `website`, `filters`, `vars`, and practical examples.

## Features

- **Comprehensive `_quarto.yml` reference** — all keys explained with examples ([_quarto-yml-reference.md](_quarto-yml-reference.md))
- **Practical configuration examples** — academic paper, blog, Reveal.js slides
- **Dual output** — HTML + PDF from a single source
- **CI/CD ready** — GitHub Actions auto-builds and deploys to GitHub Pages
- **Custom domain support** — CNAME + .nojekyll configured

## Contents

| File | Description |
|------|-------------|
| `index.qmd` | Top page |
| `content1.qmd` ~ `content5.qmd` | Content pages (Quarto notation examples) |
| `notation.qmd` | Q markdown notation guide |
| `signin.qmd` | Sign-in form demo |
| `_quarto.yml` | Main project configuration |
| `styles.css` / `custom-styles.css` | Custom styles |

## Usage

```bash
# Preview locally
quarto preview

# Render all files
quarto render

# Output goes to ./docs/
```

For detailed `_quarto.yml` reference, see [_quarto-yml-reference.md](_quarto-yml-reference.md).

## Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](CONTRIBUTING.md) and [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) first.

## License

MIT License — see the [LICENSE](LICENSE) file for details.

## Contact

GitHub: [https://github.com/watanabe3tipapa/quarto-pe](https://github.com/watanabe3tipapa/quarto-pe)
