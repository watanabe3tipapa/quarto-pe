# quarto-pe

Quarto の **`_quarto.yml` 記法** と **Q markdown 構文** をまとめたリファレンス・チートシートです。

[English](README_EN.md)

## 使い方

```bash
# ローカルでプレビュー
quarto preview

# 全ファイルをレンダリング（出力先: _site/）
quarto render
```

## 構成

- [index.qmd](index.qmd) — LP（ランディングページ）
- [reference.qmd](reference.qmd) — `_quarto.yml` 記法リファレンス
- [notation.qmd](notation.qmd) — Q markdown 記法リファレンス
- [content1-5.qmd](content1.qmd) — テンプレート集・実例

## 公開

GitHub Actions が `quarto render` を実行し、`_site/` を GitHub Pages へ自動デプロイします。

## ライセンス

MIT — 詳細は [LICENSE](LICENSE) を参照。