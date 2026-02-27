# quarto-pe

> ## Review Q markdown notation and keep writing!

![Check](https://github.com/watanabe3tipapa/quarto-pe/blob/main/assets/quarto_check.jpg)

**特に _quarto.yml_ の記法などについて追記していきます。**

備忘録なので qmdファイル もUPLOADしています。

---

＜ 追記 ＞

# `_quarto.yml` 詳細解説

## 1. `_quarto.yml` とは？

`_quarto.yml` は、Quarto プロジェクトの**ルートディレクトリ**に配置する **YAML 設定ファイル**です。

```
my-project/
├── _quarto.yml          ← プロジェクト全体の設定
├── index.qmd
├── chapter1.qmd
└── references.bib
```

これらのファイルは、以下の設定を包括的に管理できます：

- プロジェクトの種類（article、book、website、blog、presentation）
- 出力形式（HTML、PDF、Word、EPUB、revealjs）
- テーマやスタイル
- メタデータ（タイトル、著者、日付、ISBN 等）
- ビルド動作
- フィルターや拡張機能

---

## 2. 基本的な構造

```yaml
# ============================================
# プロジェクト全体のメタデータ
# ============================================
project:
  type: website          # プロジェクトの種類
  output-dir: _site      # 出力ディレクトリ

# ドキュメントのデフォルト設定
defaults:
  format:
    html:
      theme: default
      toc: true

# グローバルな YAML front matter（全ファイルに適用）
title: "My Project"
author: "watanabe3tipapa"
date: today

# 出力形式の詳細設定
format:
  html:
    code-fold: true
    toc: true
  pdf:
    documentclass: article
```

---

## 3. プロジェクト種類（`project.type`）

| 種類 | 説明 | デフォルト出力ディレクトリ |
|------|------|--------------------------|
| `website` | 静的なウェブサイト | `_site` |
| `book` | 書籍（複数章） | `_book` |
| `blog` | ブログ | `_site` |
| `presentation` | スライドショー | `_slides` |
| `article` | 单一の記事/論文 | ファイルと同じ階層 |

```yaml
project:
  type: book
  output-dir: _book
```

---

## 4. 出力形式設定（`format`）

### 4.1 単一形式

```yaml
format:
  html:
    toc: true
    code-fold: true
    theme: [cosmo, bootstrap]
```

### 4.2 複数形式（同時出力）

```yaml
format:
  html:
    toc: true
  pdf:
    documentclass: report
    geometry: margin=1in
  docx:
    reference-doc: template.docx
```

### 4.3 よく使うオプション一覧

#### HTML 出力

```yaml
format:
  html:
    # 目次
    toc: true                    # 目次の表示
    toc-title: "Table of Contents"
    toc-depth: 3                 # 目次の深さ
    
    # コード
    code-fold: true              # コードブロックの折りたたみ
    code-link: true              # コードへのディープリンク
    highlight-style: github      # ハイライトテーマ
    
    # テーマ
    theme: [cosmo, bootstrap]    # メインテーマ + ブートstrap
    
    # 数学
    mathjax: auto
    katex: auto
    
    # SEO / メタ
    lang: ja
    meta:
      description: "説明文"
      og:image: "social-card.png"
    
    # ナビゲーション
    navbar:
      background: primary
      left:
        - text: "Home"
          href: index.qmd
        - text: "About"
          href: about.qmd
```

#### PDF 出力

```yaml
format:
  pdf:
    # ドキュメントクラス
    documentclass: article        # article, report, book, memoir
    classoption: [draft, oneside]
    
    # 余白
    geometry:
      - margin=1in
      - top=1.5in
    
    # フォント
    mainfont: "Noto Serif CJK JP"
    sansfont: "Noto Sans CJK JP"
    monofont: "Source Han Code JP"
    fontsize: 11pt
    
    # ヘッダー/フッター
    header-includes: |
      \usepackage{fancyhdr}
      \pagestyle{fancy}
    
    # 図表
    fig-align: center
    tbl-cap-location: top
    
    # 番号付け
    number-sections: true
    sec-number-depth: 2
```

#### Word 出力

```yaml
format:
  docx:
    reference-doc: my-template.docx  # Word テンプレート
    toc: true
    toc-depth: 2
```

#### Reveal.js スライド

```yaml
format:
  revealjs:
    theme: simple                  # テーマ
    transition: slide              #  TRANSITION 効果
    slide-number: true
    code-fold: true
    embed-resources: true          # 単一HTMLファイルに埋め込み
    header-includes: |
      <style>
      .reveal { font-size: 24px; }
      </style>
```

---

## 5. `project` キー（プロジェクト全体設定）

```yaml
project:
  # プロジェクトの種類（必須）
  type: website
  
  # 出力ディレクトリ
  output-dir: _site
  
  # .render 実行時に自動実行
  render:
    - "*.qmd"           # 全ての .qmd
    - "!.draft.qmd"    # 除外ファイル
  
  #  recursos（リソース） の処理
  resources:
    - "images/*"
    - "data/*.csv"
    - "style.css"
  
  # ファイルの関連付け（ナレッジパネル）
  execute:
    timeout: 30         # コード実行のタイムアウト（秒）
    
  # 事前/事後スクリプト
  pre-render: script-pre.R
  post-render: script-post.R
```

---

## 6. `defaults` キー（デフォルト設定）

すべてのファイルに適用されるデフォルト設定を上書きできます。

```yaml
defaults:
  # 全ての出力形式に適用
  output-extensions: [html, pdf]
  
  # format ごとにデフォルト指定
  format:
    html:
      theme: flatly
      toc: true
      code-fold: true
      
    pdf:
      documentclass: article
      number-sections: true
      
  # チャンクのデフォルトオプション
  execute:
    echo: true
    warning: false
    fig-width: 6
    fig-height: 4
```

### ファイル単位での上書き

個別の `.qmd` ファイルでデフォルトをオーバーライド可能：

```yaml
---
# index.qmd での上書き
format:
  html:
    theme: darkly    # デフォルトの flatly を上書き
---
```

---

## 7. 書籍（book）プロジェクトの専用設定

```yaml
project:
  type: book

book:
  # 書籍のメタデータ
  title: "私の本"
  subtitle: "サブタイトル"
  author: "浦島太郎"
  date: "2025-01-01"
  version: "1.0.0"
  isbn: "978-4-123456-78-9"
  
  # 章の順序（ファイル名）
  chapters:
    - index.qmd           # はじめに
    - part: intro.qmd     # パートヘッダー
    - 01-introduction.qmd
    - 02-literature.qmd
    - part: methods.qmd
    - 03-methodology.qmd
    - 04-results.qmd
    - 05-discussion.qmd
    - conclusion.qmd
    - references.qmd
    - appendix:
        - app-a.qmd
        - app-b.qmd
  
  # 目次の設定
  toc: true
  toc-depth: 2
  toc-title: "目次"
  
  # 参照先（相互参照）
  reference-location: margin  # margin / block / section
  
  # ブックタイプ
  reader-mode: true
  
  # ダウンロード可能リソース
  downloads: [pdf, epub]
  
  # Google Analytics
  google-analytics: "G-XXXXXXXXXX"
  
  # 共有リンク
  sharing:
    x: true
    facebook: true
```

---

## 8. ウェブサイト/ブログ専用設定

```yaml
project:
  type: website
  
website:
  title: "私のウェブサイト"
  subtitle: "サブタイトル"
  description: "このウェブサイトについて"
  site-url: "https://example.com"
  
  # ナマリゲーションメニュー
  navbar:
    title: "サイトタイトル"
    background: primary
    search: true
    left:
      - text: "ホーム"
        href: index.qmd
      - text: "ブログ"
        href: blog/index.qmd
      - text: "ページ"
        menu:
          - text: "概要"
            href: about.qmd
          - text: "お問い合わせ"
            href: contact.qmd
    right:
      - icon: github
        href: https://github.com/username
      - icon: twitter
        href: https://x.com/username
        
  # サイドバー
  sidebar:
    title: "ナビゲーション"
    background: light
    width: 250px
    contents:
      - text: "はじめに"
        href: intro.qmd
      - text: "チュートリアル"
        contents:
          - text: "Step 1"
            href: tutorial1.qmd
          - text: "Step 2"
            href: tutorial2.qmd
          
  # フッター
  footer: "© 202X 名前. All rights reserved."
  
  # ソーシャルカード（OG画像）
  open-graph: true
  twitter-card:
    creator: "@username"
    
  # サイトマップ
  sitemap: true
  
  # RSS
  rss: "feed.xml"
```

---

## 9. フィルタと拡張機能

### 9.1 組み込みフィルター

```yaml
filters:
  - adjustbox
  - diagbox
  - "quarto-diagrams"  # Mermaid 図
```

### 9.2 外部フィルター（Lua）

```yaml
filters:
  - location: my-filter.lua
  - https://raw.githubusercontent.com/user/repo/main/filter.lua
```

### 9.3 テーマ拡張

```yaml
format:
  html:
    theme: 
      - custom.scss
      - cosmo
    css: styles.css
```

---

## 10. 変数（Variables）

YAML で定義した変数は、`.qmd` ファイル内で `{{ var_name }}` で参照可能。

```yaml
# _quarto.yml
project:
  type: website

vars:
  author: "浦島太郎"
  email: "taro@example.com"
  org: "XYZ大学"
  year: 2025
```

```qmd
---
title: "研究論文"
---

著者: {{< var author >}}
所属: {{< var org >}}
メール: {{< var email >}}
```

---

## 11. 環境変数と条件付き設定

```yaml
project:
  type: website

# 環境変数による条件分岐
quartodoc:
  output: |
    #ifndef QUARTO_PROD
    {html}
    #endif
```

---

## 12. 実践的な設定例

### 12.1 学術論文（PDF + HTML 同時出力）

```yaml
title: "機械学習による天気予測"
author:
  - name: 浦島太郎
    orcid: 0000-0000-0000-0000
    affiliation: XYZ大学
  - name: 此花姫子
    affiliation: ABC大学
    
date: today
bibliography: references.bib
link-citations: true

project:
  type: article

format:
  html:
    toc: true
    number-sections: true
    code-fold: true
    citation-location: margin
    
  pdf:
    documentclass: article
    classoption: [journal, letter]
    geometry: margin=1in
    number-sections: true
    header-includes: |
      \usepackage{authblk}
      \author{浦島太郎\thanks{XYZ大学}}
      \author{此花姫子\thanks{ABC大学}}
    keep-tex: true

execute:
  echo: false
  warning: false
  message: false
```

### 12.2 BLOG（Blog with Quarto）

```yaml
project:
  type: website
  output-dir: _site

website:
  title: "データサイエンス日記"
  description: "Python と R によるデータ分析メモ"
  site-url: "https://datascience-blog.net"
  
  navbar:
    background: dark
    left:
      - text: "ホーム"
        href: index.qmd
      - text: "記事"
        href: blog/index.qmd
      - text: "タグ"
        menu:
          - text: "Python"
            href: tags/python.qmd
          - text: "R"
            href: tags/r.qmd
    right:
      - icon: github
        href: https://github.com/username
      - icon: rss
        href: index.xml
        
  sidebar:
    title: "最近の投稿"
    contents: blog/*.qmd
    limit: 5
    
  footer: "© 202X 名前. CC BY 4.0"
  
  rss: feed.xml
  
format:
  html:
    theme: [cosmo, darkly]
    code-fold: true
    highlight-style: github-dark
    
blog:
  post-date-format: "yyyy年MM月dd日"
  listing: blog/index.qmd
  
execute:
  freeze: auto
```

### 12.3 スライド発表（Reveal.js）

```yaml
title: "研究発表タイトル"
author: "浦島太郎"
institute: "XYZ大学"
date: "2025年1月15日"

project:
  type: presentation

format:
  revealjs:
    theme: simple
    transition: slide
    background-transition: fade
    slide-number: c/t
    code-fold: true
    code-link: true
    embed-resources: true
    output-file: presentation.html
    
    # ヘッダー/フッター
    header: |
      <div style="position: absolute; top: 10px; right: 10px; font-size: 20px;">
        浦島太郎 - 2025
      </div>
      
    # フォントサイズ調整
    fontsize: 24pt
    
    # チャンクオプションのデフォルト
execute:
  echo: true
  output: true
```

---

## 13. 設定のデバッグと検証

### 13.1 設定のプレビュー

```bash
# プロジェクト情報の表示
quarto check project

# 設定の検証
quarto inspect _quarto.yml
```

### 13.2 設定ファイルのパス確認

```bash
# プロジェクトルートを確認
quarto config
```

---

## 14.  Tips & Best Practices

| ポイント | 説明 |
|---------|------|
| **ファイル名は `_quarto.yml`** | アンダースコア始まり。ダッシュ（`-`）ではない。 |
| **インデントはスペース2つ** | YAML の惯例に従う。 |
| **コメントアウト** | `#` でコメント可能 |
| **環境ごとの設定** | `_quarto.local.yml` でローカル上書き（`.gitignore` に追加） |
| **output-dir の除外** | `_site`, `_book` などは `.gitignore` に追加 |
| **変数活用** | 繰り返し登場する author 名などは変数に切り出す |
| **テーマの継承** | 複数のテーマを配列で指定するとカスケード適用 |

---

## 15. まとめ

`_quarto.yml` は Quarto プロジェクトの **コアコンフィグレーション** です。

| キー | 役割 |
|------|------|
| `project` | プロジェクトの種類、出力ディレクトリ、リソース |
| `format` | 出力形式별（HTML、PDF、Word、Reveal.js）詳細設定 |
| `defaults` | すべてのファイルに適用されるデフォルト値 |
| `book` | 書籍専用の章構成、目次に 관한設定 |
| `website` | ウェブサイト/ブログのナビゲーション、サイドバー |
| `filters` | Lua フィルターの読み込み |
| `vars` | ドキュメント内で使用する変数定義 |

これらを適切に組み合わせることで、**1つのソースから多様な出力** を効率的に生成できる Quarto の真価を発揮できます。

---
