# quarto-pe

A reference / cheat-sheet for Quarto **`_quarto.yml` notation** and **Q markdown syntax**.

[日本語](README.md)

## Usage

```bash
# Live preview
quarto preview

# Render all files (output: _site/)
quarto render
```

## Contents

- [index.qmd](index.qmd) — Landing page
- [reference.qmd](reference.qmd) — `_quarto.yml` notation reference
- [notation.qmd](notation.qmd) — Q markdown notation reference
- [content1-5.qmd](content1.qmd) — Template collections & examples

## Deployment

GitHub Actions runs `quarto render` and auto-deploys `_site/` to GitHub Pages.

## License

MIT — see [LICENSE](LICENSE).