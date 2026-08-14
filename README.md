# quarto-pe

**Quarto, 体系化。**

quarto-pe は、Quarto の設定ファイル **`_quarto.yml` 記法** と本文の **Q markdown 構文** を、ひとつの場所にまとめたチートシート兼リファレンスサイトです。公式仕様に基づく実在キーだけを体系的に解説し、コピペで使えるテンプレート集・実動サンプル・実サイトの事例を同梱します。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Version](https://img.shields.io/badge/version-v0.4.0-blue.svg)](https://github.com/watanabe3tipapa/quarto-pe/releases)
[![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-live-blue.svg)](https://watanabe3tipapa.github.io/quarto-pe/)
[![GitHub](https://img.shields.io/github/issues/watanabe3tipapa/quarto-pe.svg)](https://github.com/watanabe3tipapa/quarto-pe/issues)

[日本語](README.md) | [English](README_EN.md)

## コンセプト

### なぜ「pe」なのか

Quarto は高機能な一方、`_quarto.yml` のキーは `project` / `format` / `website` / `book` / `execute` などに散在し、ネット上の情報には実在しない記法や誤ったコマンドも混ざっています。

quarto-pe はそれらの情報を「**個人備忘録（Personal Edition）として精査**」し、公式仕様に基づく実在キー・実コマンドだけを体系的にまとめます。検索のたびに不確かな情報を渡り歩く代わりに、1つの場所で正確な答えにたどり着けます。

| 営み | quarto-pe の対応物 |
|---|---|
| 設定キーを調べる | [_quarto.yml 記法リファレンス](https://watanabe3tipapa.github.io/quarto-pe/reference.html) が `project` / `format` / `website` / `book` / `execute` / `vars` を体系化 |
| 本文の書き方を学ぶ | [Q markdown 記法](https://watanabe3tipapa.github.io/quarto-pe/notation.html) が見出し・Div・Callout・相互参照・数式・変数を実サンプル付きで解説 |
| 最初の設定を用意する | [設定テンプレート](https://watanabe3tipapa.github.io/quarto-pe/content3.html) から好みの構成をコピペ |
| 動的コンテンツを試す | [コード実行・動的コンテンツ](https://watanabe3tipapa.github.io/quarto-pe/content4.html) で R チャンク・パラメータ・Observable JS を実動体験 |
| 構造化・多形式を仕上げる | [構造化・多形式](https://watanabe3tipapa.github.io/quarto-pe/content5.html) で相互参照・Callout・レイアウト・文献管理を適用 |
| 実運用の勘所を知る | [実サイトのYAML](https://watanabe3tipapa.github.io/quarto-pe/content2.html) と [本サイトの設定](https://watanabe3tipapa.github.io/quarto-pe/content1.html) で確認 |
| 公開する | GitHub Actions による GitHub Pages への自動デプロイ |

### リファレンスは「正確さ」が命

本サイトは **実在するキー・コマンドだけ** を扱います。初版に含まれていた実在しない記法（`defaults` キー、`output-extensions`、`quarto check project`、`lang: jp` など）は全面修正済みです。キーが実際に動作することを手元の Quarto 1.3+ で検証した上で掲載しています。

- **体系化** — 実在キーをカテゴリ別に整理（旧版の誤記は全廃）
- **実動サンプル** — コードチャンク・Observable JS・相互参照がその場で動く
- **コピペで即利用** — テンプレート集から自分のプロジェクトに貼るだけ

## 特徴

- **体系化されたリファレンス**: `_quarto.yml` の全キーを `project` / `format` / `website` / `book` / `execute` / `vars` に分類して解説
- **Q markdown 記法**: 見出し・Div・Callout・相互参照・数式・変数・shortcode を実サンプル付きで解説
- **実動サンプル**: R コードチャンク・インラインコード・Observable JS をその場で実行
- **テンプレート集**: プロジェクト設定 / 出力形式 / サイト / ブログ / 書籍など 15 セクションの設定雛形
- **実例**: 本サイト自身の設定と実在サイトの YAML を解体して解説
- **正確性**: 公式仕様に基づく実在キーのみ掲載（旧版の誤記を全面修正）
- **CI 自動公開**: GitHub Actions が `quarto render` を実行し、`_site/` を GitHub Pages へ自動デプロイ

## インストール

### 前提条件

| ツール | 必要バージョン | 確認コマンド |
|---|---|---|
| [Quarto](https://quarto.org/docs/get-started/) | >= 1.3 | `quarto --version` |
| R | 任意（R チャンクを実行する場合のみ） | `R --version` |
| Git | 任意（デプロイ・貢献時） | `git --version` |

macOS では `brew install quarto` で Quarto を揃えられます。R は https://cran.r-project.org からインストールしてください。

### 1. リポジトリを取得する

```bash
git clone https://github.com/watanabe3tipapa/quarto-pe.git
cd quarto-pe
```

### 2. プレビューする

```bash
quarto preview
```

### 3. レンダリングする

```bash
quarto render
```

`_site/` に出力されます。単一ファイルだけのレンダリングは `quarto render reference.qmd` のように指定できます。

### 4. 公開する

`main` への push で GitHub Actions が自動でビルド・デプロイします。

## コンテンツ

| ページ | 内容 |
|---|---|
| [index.qmd](index.qmd) | LP（ランディングページ） |
| [reference.qmd](reference.qmd) | `_quarto.yml` 記法リファレンス |
| [notation.qmd](notation.qmd) | Q markdown 記法リファレンス |
| [content1.qmd](content1.qmd) | 本サイトの設定解説（事例） |
| [content2.qmd](content2.qmd) | 実在サイトの YAML 事例 |
| [content3.qmd](content3.qmd) | `_quarto.yml` テンプレート集 |
| [content4.qmd](content4.qmd) | コード実行・動的コンテンツのテンプレート |
| [content5.qmd](content5.qmd) | 構造化・多形式のテンプレート |

初心者の方は [リファレンス](https://watanabe3tipapa.github.io/quarto-pe/reference.html) で基本構造を押さえ、[テンプレート集](https://watanabe3tipapa.github.io/quarto-pe/content3.html) から始めるのがおすすめです。

## ドキュメント

- [_quarto.yml 記法リファレンス](https://watanabe3tipapa.github.io/quarto-pe/reference.html) — プロジェクト設定の全キー
- [Q markdown 記法](https://watanabe3tipapa.github.io/quarto-pe/notation.html) — 本文の書き方
- [テンプレート集](https://watanabe3tipapa.github.io/quarto-pe/content3.html) — 実用雛形

開発メモは [DEV-MEMO](DEV-MEMO.md)、変更履歴は [CHANGELOG](CHANGELOG.md) を参照してください。

## コントリビューション

コントリビューションは大歓迎です。本サイトは「実在キーのみ・正確に」を方針としています。誤りや不正確な記述を見つけた場合は、まず [issue](https://github.com/watanabe3tipapa/quarto-pe/issues) を開いて内容を共有してください。

1. リポジトリをフォーク
2. 機能ブランチを作成 (`git checkout -b fix/typo-in-reference`)
3. 変更をコミット (`git commit -m 'Fix typo in reference'`)
4. ブランチにプッシュ (`git push origin fix/typo-in-reference`)
5. Pull Request を作成

## 連絡先

GitHub: [https://github.com/watanabe3tipapa/quarto-pe](https://github.com/watanabe3tipapa/quarto-pe)

公開サイト: [https://watanabe3tipapa.github.io/quarto-pe/](https://watanabe3tipapa.github.io/quarto-pe/)

## ライセンス

MITライセンス — 詳細は [LICENSE](LICENSE) ファイルを参照してください。
