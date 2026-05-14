# DEV-MEMO: quarto-pe 機能評価レポート

## プロジェクト概要

| 項目 | 内容 |
|------|------|
| **名称** | quarto-pe |
| **種別** | Quarto Website プロジェクト |
| **目的** | Quarto の `_quarto.yml` 記法・Q markdown 記法の個人備忘録・リファレンス |
| **公開方法** | GitHub Pages（CNAME, .nojekyll 確認済） |

## 技術スタック

- **Quarto** (Website type) + **YAML** 設定
- **出力形式**: HTML（主） + PDF（併用）
- **テーマ**: spacelab（HTML）
- **カスタムCSS**: 2系統（`styles.css` / `custom-styles.css`）
- **CI/CD**: GitHub Actions — `quarto-dev/quarto-actions/setup@v2` + TinyTeX（PDF用）
- **レンダリングエンジン**: Pandoc（Quarto 内蔵）

## ファイル構成

```
quarto-pe/
├── _quarto.yml               # プロジェクト全体設定（core）
├── _quarto.local.yml         # ローカル上書き設定（.gitignore 対象）
├── index.qmd                 # トップページ
├── content1-5.qmd            # コンテンツページ（全5ファイル）
├── notation.qmd              # Quarto 記法メモ
├── signin.qmd                # サインインページ（フォーム設置）
├── styles.css                # カスタムスタイル（方眼紙背景）
├── custom-styles.css         # 別系統カスタムスタイル
├── assets/                   # 画像4点（スクリーンショット類）
├── docs/                     # ビルド出力先（_quarto.yml で output-dir: docs 指定）
├── tmp/                      # 一時作業ディレクトリ
└── .github/workflows/static.yml  # GitHub Pages 自動デプロイ
```

## 機能評価

### 既存の強み

| 観点 | 評価 |
|------|------|
| **ドキュメント網羅性** | `_quarto.yml` の全キー（project / format / defaults / book / website / filters / vars）を15セクションで詳細解説。公式リファレンス級の情報量。 |
| **実践例の充実度** | 学術論文（PDF+HTML同時出力）、Blog、Reveal.js スライドの3パターンの設定例を完備。コピペで即利用可能。 |
| **デュアル出力** | HTML + PDF を同一ソースから同時出力。各 qmd ファイルに両形式の front matter を定義。 |
| **CI/CD 完備** | GitHub Actions で push → quarto render → GitHub Pages デプロイまで自動化。TinyTeX で PDF 生成も対応。 |
| **カスタムドメイン対応** | CNAME + .nojekyll により独自ドメイン運用が可能。 |
| **ナビゲーション設計** | navbar にドロップダウンメニュー、検索、GitHub/サインインリンクを完備。 |
| **レスポンシブ対応** | Quarto 標準テーマ（spacelab）+ CSS カスタマイズ。 |

### 改善点（本タスクで対応）

| 問題 | 対応 |
|------|------|
| README がドキュメントそのものでプロジェクト説明がない | `README.md` をプロジェクト説明に書き換え、ドキュメント本体は `docs/` に移動 |
| 英日バイリンガル未対応 | `README_ja.md` を新規追加、言語切り替えリンク設置 |
| バッジ未設定 | License / Stars / Last commit / PRs welcome / Maintenance / Changelog のバッジを追加 |
| LICENSE 未整備 | MIT ライセンスを追加 |
| CONTRIBUTING / CODE_OF_CONDUCT / SECURITY 未整備 | テンプレートベースで一括作成（英日対応） |
| CHANGELOG 未整備 | Keep a Changelog 形式で作成 |
| Issue/PR テンプレート未整備 | bug_report / feature_request / PR テンプレートを追加 |
| OGP画像未設定 | assets/ に OGP 画像を追加予定 |

### 注意点・リスク

| 項目 | 内容 |
|------|------|
| `docs/` にビルド済みHTMLが存在 | ビルド出力と手動ドキュメントが混在している。移動先の `docs/_quarto-yml-reference.md` は qmd ではなく md なので、quarto render の対象外。 |
| `_quarto.local.yml` | ローカル固有設定。`.gitignore` 対象で管理外だが、チーム開発時には注意。 |
| `content1-5.qmd` の front matter | YAML に重複・タイポあり（Content4/5 の description に "Content3" と記載）。後日リファクタリング推奨。 |
| CSS の実装状況 | `custom-styles.css` はほぼ空。`styles.css` は方眼紙デザインだが一部未完成。 |

## 今後の拡張アイデア（任意）

- SNS シェアボタンの追加
- タグ/カテゴリによる記事整理
- OGP画像の作成と設定
- サイト内検索の強化
- 多言語ページ（英語版 qmd）の追加
