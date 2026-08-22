# quarto-pe

**Quarto、体系化。**

[サイトを見る](https://watanabe3tipapa.github.io/quarto-pe/)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE) [![Version](https://img.shields.io/badge/version-v0.4.0-blue.svg)](https://github.com/watanabe3tipapa/quarto-pe/releases) [![GitHub Pages](https://img.shields.io/badge/GitHub%20Pages-live-blue.svg)](https://watanabe3tipapa.github.io/quarto-pe/) [![GitHub](https://img.shields.io/github/issues/watanabe3tipapa/quarto-pe.svg)](https://github.com/watanabe3tipapa/quarto-pe/issues)

[日本語](README.md) | [English](README_EN.md)

概要

quarto-pe は Quarto の設定ファイル（`_quarto.yml`）に使われるキー表記と、本文で使う Q markdown 記法を1か所にまとめたチートシート兼リファレンスサイトです。公式仕様に基づく実在キーのみを体系化して解説し、コピペで使えるテンプレートや実動サンプル、実サイト事例を同梱します。

コンセプト

- 個人備忘録（Personal Edition）として、ネット上に散在する不確かな記法や誤情報を排し、公式仕様に基づく実在キー・実コマンドだけを掲載します。
- 手元の Quarto（README 記載の検証環境として Quarto 1.3+ を参照）で動作確認した実在キーを優先して体系化しています。

主な特徴

- 体系化されたリファレンス: `_quarto.yml` のキーを `project` / `format` / `website` / `book` / `execute` / `vars` 等に分類して解説
- Q markdown 記法: 見出し、Div、Callout、相互参照、数式、変数、shortcode をサンプル付きで解説
- 実動サンプル: R チャンク、インラインコード、Observable JS 等の実動例を収録
- テンプレート集: プロジェクト設定・出力形式・サイト・ブログ・書籍などの雛形（約15セクション）
- 実例: 本サイト自身や実在サイトの YAML を分解して解説
- CI 自動公開: GitHub Actions による `quarto render` と GitHub Pages への自動デプロイ（README 内の記述に基づく）
- 正確性重視: 実在しない旧記法・誤記を修正し、実在キーのみを掲載

前提条件（事実ベース）

| ツール | 必要バージョン | 確認コマンド |
|---|---:|---|
| Quarto | >= 1.3 | `quarto --version` |
| R | 任意（R チャンクの実行時） | `R --version` |
| Git | 任意（デプロイ・貢献時） | `git --version` |

macOS では `brew install quarto` で Quarto を入手できる旨が README に記載されています。R は CRAN（https://cran.r-project.org）から入手してください。

開始方法（README に記載されている手順のみ）

1. リポジトリを取得

```bash
git clone https://github.com/watanabe3tipapa/quarto-pe.git
cd quarto-pe
```

2. プレビュー

```bash
quarto preview
```

3. レンダリング

```bash
quarto render
```

- レンダリング結果は `_site/` に出力されます。単一ファイルのレンダリングは `quarto render reference.qmd` のようにファイル名を指定して実行できます（README の記述に基づく）。
- main ブランチへの push による自動ビルド・デプロイは README にて言及されています。

リポジトリの主な内容（README に記載のファイル）

- index.qmd — ランディングページ
- reference.qmd — `_quarto.yml` 記法リファレンス
- notation.qmd — Q markdown 記法リファレンス
- content1.qmd — 本サイトの設定解説（事例）
- content2.qmd — 実在サイトの YAML 事例
- content3.qmd — `_quarto.yml` テンプレート集
- content4.qmd — コード実行・動的コンテンツのテンプレート
- content5.qmd — 構造化・多形式のテンプレート

関連ドキュメント

- リファレンス: https://watanabe3tipapa.github.io/quarto-pe/reference.html
- Q markdown 記法: https://watanabe3tipapa.github.io/quarto-pe/notation.html
- テンプレート集: https://watanabe3tipapa.github.io/quarto-pe/content3.html
- 開発メモ: DEV-MEMO.md
- 変更履歴: CHANGELOG.md

コントリビューション

貢献歓迎。README に記載の手順をベースにしています。

1. リポジトリをフォーク
2. 機能ブランチを作成（例: `git checkout -b fix/typo-in-reference`）
3. 変更をコミット（例: `git commit -m 'Fix typo in reference'`）
4. ブランチにプッシュ（`git push origin fix/typo-in-reference`）
5. Pull Request を作成

誤りや不正確な記述を見つけた場合は、まず issue を開いて内容を共有してください: https://github.com/watanabe3tipapa/quarto-pe/issues

連絡先

- GitHub: https://github.com/watanabe3tipapa/quarto-pe
- 公開サイト: https://watanabe3tipapa.github.io/quarto-pe/

ライセンス

本リポジトリは MIT ライセンスです。詳細は LICENSE ファイルを参照してください。

開発・保守状態（README に基づく記述）

- README によれば GitHub Actions による自動デプロイが設定されており、公開サイトが稼働しています。リポジトリはアーカイブされていません（archived: false）。
