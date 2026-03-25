# 東京医療減災Labo 実践知の体系

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

> **20年の実践から生まれた災害対応力向上の完全体系**  
> 理念・実践・戦略の3つの視点から、医療機関の災害対応力を高める知識を体系化

## 📚 概要

東京医療減災Laboが20年以上にわたる災害対応力向上研修の実践から導き出した、3つの核心的な知識体系を公開します。あわせて、よろず相談AIと減災カレンダーHDMGへのアクセス窓口も提供しています。

- **哲学五箇条** - 研修の理念（Why）
- **訓練企画10原則** - 実践の方法（How）
- **動ける60点 > 動けない100点** - 組織戦略とエビデンス（What & Evidence）
- **よろず相談AI** - 過去の相談事例173件をAIで検索
- **減災カレンダーHDMG** - 自己研修テキスト申込

## 🌐 アクセス

**公開サイト**: [https://hdmg2004-ux.github.io/tokyo-gensai-labo](https://hdmg2004-ux.github.io/tokyo-gensai-labo)

## 📁 プロジェクト構造

```
.
├── README.md                           # このファイル
├── technical-specification-v2.md       # 技術仕様書
├── LICENSE.md                          # ライセンス情報
├── docs/                               # 公開Webサイト（GitHub Pages）
│   ├── index.html                     # トップページ（ポータル）
│   ├── philosophy.html                # 災害対応力向上研修 哲学五箇条
│   ├── principles.html                # 訓練企画10原則
│   └── movable-60-vs-perfect-100.html # 動ける60点 > 動けない100点
└── [その他のプロジェクトファイル]
```

## 📖 コンテンツ詳細

### 1. 災害対応力向上研修 哲学五箇条
**ファイル**: [`docs/philosophy.html`](docs/philosophy.html)  
**テーマ**: 理念（Why）

研修の背後にある5つの原則：
1. すべての反応に、価値がある（多様性尊重）
2. 知っていることと、できることは違う（体験重視）
3. 現場で使えなければ、意味がない（現場適用）
4. 一人の天才より、チームの凡人（協働創造）
5. 研修は、終わりではなく、始まりである（継続成長）

### 2. 訓練企画10原則
**ファイル**: [`docs/principles.html`](docs/principles.html)  
**テーマ**: 実践（How）

実効性のある訓練を作る10の原則：OODAループ、失敗から学ぶ、記録と共有、目的の明確化、計画より実行、前向きに終わる、6〜8割の完成度、アクション・カード、3ない訓練、3回の出だし訓練

### 3. 動ける60点 > 動けない100点
**ファイル**: [`docs/movable-60-vs-perfect-100.html`](docs/movable-60-vs-perfect-100.html)  
**テーマ**: 戦略とエビデンス（What & Evidence）

推奨度9.25が実践率2.5になる「70%ギャップ」の原因と解決策。

### 4. よろず相談AI
**URL**: [https://yorozu-chat.vercel.app/](https://yorozu-chat.vercel.app/)  
**テーマ**: 知識検索

2022年から開催している病院災害対策の専門相談会。これまでの相談事例173件の知見をAIが24時間検索できる形で提供。index.htmlからリンク。

### 5. 減災カレンダーHDMG
**テーマ**: 自己研鑽資料申込

病院災害対策の基本技能を体系的に学ぶ自己研修テキスト。Googleフォームから申込・PDFダウンロード。index.htmlからリンク。

## 🚀 使い方

### ローカルで閲覧
```bash
git clone [このリポジトリのURL]
cd [リポジトリ名]/docs
open index.html  # macOS
```

### GitHub Pagesで公開
1. Settings → Pages
2. Branch: `main` / Folder: `/docs`
3. Save

## 🛠️ 技術スタック

- **HTML5** / **CSS3** / **Vanilla JavaScript**
- 依存関係なし（完全スタンドアロン）

## 📄 ライセンス

### コンテンツ: CC BY-NC-SA 4.0
著作権者: 中島康 / 東京医療減災Labo

### コード: MIT License

## 👤 著者

**中島 康（Yasushi Nakajima）**  
東京医療減災Labo / ©HDMG2004 2026

## 📧 お問い合わせ

**Email**: [tbk_gensai_labo@tmhp.jp](mailto:tbk_gensai_labo@tmhp.jp)

## 🔄 更新履歴

### Version 3.0 (2026-03-25)
- index.htmlによろず相談AI・減災カレンダーHDMGカードを追加
- 「ツールとリソース」セクションを新設（課題別ガイドと分離）
- 「3つまとめて開く」セクションを削除
- HDMG_DESIGN_SYSTEMのカラー変数に統一

### Version 2.0 (2026-02-10)
- プロジェクト構造を`docs/`フォルダに整理
- ファイル名を英語表記に統一（GitHub対応）

### Version 1.0 (2025-11-04)
- 初版公開

---

**Made with ❤️ by 東京医療減災Labo**
