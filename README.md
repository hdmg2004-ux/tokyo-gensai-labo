# 東京医療減災Labo 実践知の体系

[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

> **20年の実践から生まれた災害対応力向上の体系**
> 理念・実践・戦略の3つの視点と、病院で使える無償ツールへの入口

## 🌐 公開サイト

https://hdmg2004-ux.github.io/tokyo-gensai-labo/

GitHub Pages（Branch: `main` / Folder: `/docs`）。`main` に push すると数分で反映されます。

## 📚 載せているもの

### 課題別ガイド（本リポジトリにページがある）

| ページ | テーマ | ファイル |
|---|---|---|
| 災害対応力向上研修 哲学五箇条 | 理念（Why） | [`docs/philosophy.html`](docs/philosophy.html) |
| 訓練企画10原則 | 実践（How） | [`docs/principles.html`](docs/principles.html) |
| 動ける60点 ＞ 動けない100点 | 戦略とエビデンス（What） | [`docs/movable-60-vs-perfect-100.html`](docs/movable-60-vs-perfect-100.html) |

### 病院の災害対応ツール（紹介とリンクのみ）

本体・説明書の**正本は各ツールのリポジトリ**です。ポータルには紹介カードと固定リンク（`releases/latest`）だけを置き、ファイルは複製しません。

| ツール | 現行版 | リポジトリ | 入手先 |
|---|---|---|---|
| 発災時行動判断支援ツール | v2.3 | [hdmg2004-ux/bcp-disaster](https://github.com/hdmg2004-ux/bcp-disaster) | Web版 https://bcp-disaster.vercel.app/ ／ Releases（`bcp_disaster.html`・`guide_bcp_disaster.pdf`） |
| 病院医療継続 活動ツール | β v11.1 | [hdmg2004-ux/bcp-disaster-med](https://github.com/hdmg2004-ux/bcp-disaster-med) | Releases（`bcp_disaster_med.html`・`guide_bcp_disaster_med.pdf`） |

新しい版を Release したときにポータル側で直すのは、`docs/index.html` のカードにある版表記（`app-version`）だけです。リンクは latest を指すので変更不要です（Asset 名を変えた場合は除く）。

### ツールとリソース（外部リンク）

- よろず相談AI — https://yorozu-chat.vercel.app/
- 減災カレンダーHDMG — 自己研修テキスト申込（Googleフォーム）
- 防災ジョジョ — ラジオ番組
- 問う日和 — 2週間に一度のフォローアップメール（Googleフォーム）

## 📁 構成

```
.
├── README.md        このファイル
├── LICENSE.md       ライセンス（コンテンツ CC BY-NC-SA 4.0／コード MIT）
├── docs/            公開サイト（GitHub Pages）
│   ├── index.html                     ポータル
│   ├── philosophy.html                哲学五箇条
│   ├── principles.html                訓練企画10原則
│   ├── movable-60-vs-perfect-100.html 動ける60点
│   ├── images/                        ロゴ画像
│   └── favicon・manifest・アイコン類
└── notes/           公開しない作業用の資料
    ├── technical-specification-v3.md  技術仕様（v3.0 時点）
    ├── HDMG_DESIGN_SYSTEM.md          デザインシステム
    └── 既存コンテンツ追加提案_20260403.md  JADM31 WS データにもとづく追記案（未反映）
```

- 法人サイト https://gensai-labo.tokyo/ のソースは別リポジトリ [hdmg2004-ux/gensai-labo.tokyo](https://github.com/hdmg2004-ux/gensai-labo.tokyo) です。

## 📝 編集するとき

- 新しいページ → `docs/` に HTML を作り、`docs/index.html` からリンク
- 色・書体は `notes/HDMG_DESIGN_SYSTEM.md` に合わせる
- 依存ライブラリなし（HTML／CSS／Vanilla JS）

## 📄 ライセンス・著作権

© 東京医療減災Labo 2025–

コンテンツは CC BY-NC-SA 4.0、コードは MIT License。紹介しているツールの本体・説明書は本リポジトリに含まれず、各リポジトリの LICENSE に従います。詳しくは [LICENSE.md](LICENSE.md)。

## 📧 お問い合わせ

hdmg2004@gmail.com

## 🔄 更新履歴

### Version 3.1（2026-10-29）
- ポータルに「病院の災害対応ツール」を新設（発災時行動判断支援ツール v2.3／病院医療継続 活動ツール β v11.1 の紹介とリンク）
- 著作表示・連絡先を「© 東京医療減災Labo」「hdmg2004@gmail.com」に統一
- ファイル整理：`docs_old/`・`HP/`（gensai-labo.tokyo の旧下書き）・汎用のデプロイ手順・`PROJECT_STRUCTURE.md`（本READMEに統合）を削除、作業用資料を `notes/` へ移動

### Version 3.0（2026-03-25）
- よろず相談AI・減災カレンダーHDMGカードを追加、「ツールとリソース」を新設

### Version 2.0（2026-02-10）
- `docs/` フォルダに整理、ファイル名を英語表記に統一

### Version 1.0（2025-11-04）
- 初版公開
