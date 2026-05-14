<!-- badges -->
[![License](https://img.shields.io/github/license/watanabe3tipapa/quarto-pe.svg)](LICENSE)
[![Stars](https://img.shields.io/github/stars/watanabe3tipapa/quarto-pe.svg)](https://github.com/watanabe3tipapa/quarto-pe/stargazers)
[![Last commit](https://img.shields.io/github/last-commit/watanabe3tipapa/quarto-pe/main.svg)](https://github.com/watanabe3tipapa/quarto-pe/commits/main)
[![PRs welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)
[![Maintenance](https://img.shields.io/badge/Maintenance-Active-brightgreen.svg)](https://github.com/watanabe3tipapa/quarto-pe)
[![Changelog](https://img.shields.io/badge/Changelog-Keep%20a%20Changelog-green.svg)](CHANGELOG.md)

[English](README.md) | [日本語](README_ja.md)

# quarto-pe

**Quarto の `_quarto.yml` 記法**と **Q markdown 構文**に関する個人備忘録プロジェクトです。

`project` / `format` / `defaults` / `book` / `website` / `filters` / `vars` など、Quarto プロジェクト設定のチートシート兼リファレンスとして活用できます。

## 特徴

- **`_quarto.yml` 網羅的リファレンス** — 全キーを実例付きで解説（[docs/_quarto-yml-reference.md](docs/_quarto-yml-reference.md)）
- **実践的な設定例** — 学術論文、Blog、Reveal.js スライドのテンプレート完備
- **デュアル出力** — 1つのソースから HTML + PDF を同時生成
- **CI/CD 対応** — GitHub Actions で自動ビルド＆GitHub Pages デプロイ
- **カスタムドメイン対応** — CNAME + .nojekyll 設定済み

## コンテンツ一覧

| ファイル | 説明 |
|----------|------|
| `index.qmd` | トップページ |
| `content1.qmd` ~ `content5.qmd` | コンテンツページ（Quarto 記法サンプル） |
| `notation.qmd` | Q markdown 記法ガイド |
| `signin.qmd` | サインインフォームデモ |
| `_quarto.yml` | プロジェクトメイン設定 |
| `styles.css` / `custom-styles.css` | カスタムスタイル |

## 使い方

```bash
# ローカルでプレビュー
quarto preview

# 全ファイルをレンダリング
quarto render

# 出力先: ./docs/
```

`_quarto.yml` の詳細リファレンスは [docs/_quarto-yml-reference.md](docs/_quarto-yml-reference.md) を参照してください。

## コントリビューション

コントリビューションは大歓迎です！まず [CONTRIBUTING.md](CONTRIBUTING.md) と [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) をお読みください。

## ライセンス

MITライセンス — 詳細は [LICENSE](LICENSE) ファイルを参照してください。

## 連絡先

GitHub: [https://github.com/watanabe3tipapa/quarto-pe](https://github.com/watanabe3tipapa/quarto-pe)
