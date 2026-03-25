# 東京医療減災Labo 実践知の体系 - 技術仕様書

**バージョン**: 3.0
**最終更新**: 2026年3月25日

---

## 1. 概要

東京医療減災Laboの資料（哲学五箇条・訓練企画10原則・動ける60点）とポータルページ（index.html）を、縦スクロール形式・目次機能付き・レスポンシブ対応のWebページとして実装。index.htmlはよろず相談AIと減災カレンダーHDMGへの導線も兼ねる。

### 作成ファイル
- `index.html` - トップページ（ポータル）
- `philosophy.html` - 災害対応力向上研修 哲学五箇条
- `principles.html` - 訓練企画10原則
- `movable-60-vs-perfect-100.html` - 動ける60点 > 動けない100点

---

## 2. 技術スタック

- **HTML5** / **CSS3** / **Vanilla JavaScript**
- フレームワーク・ライブラリ不使用
- 外部依存なし（完全スタンドアロン）

---

## 3. デザイン仕様

### カラースキーム（HDMG_DESIGN_SYSTEM準拠）

```css
/* プライマリカラー（燕子花色） */
--primary: #3e62ad;
--primary-hover: #2d4a8c;
--primary-light: #5c7fc4;

/* 背景 */
--bg-secondary: #f9fafb;
--bg-tertiary: #f3f4f6;   /* ツールセクション背景 */

/* アクセント */
--accent-red: #dc143c     /* 「災」の強調 */
```

### index.htmlのセクション構成

| セクション | 背景色 | 内容 |
|-----------|--------|------|
| ヘッダー | #1e3c72→#3e62ad グラデーション | タイトル・サブタイトル |
| イントロ | #fafafa | 三角形ナビ（理念・実践・戦略） |
| 課題別ガイド | white | 3カード（既存コンテンツ） |
| ツールとリソース | #f3f4f6 | 2カード（よろず・減災カレンダー） |
| フッター | #3e62ad | 連絡先 |

---

## 4. 外部リンク

| カード | リンク先 |
|--------|---------|
| よろず相談AI | https://yorozu-chat.vercel.app/ |
| 減災カレンダーHDMG | https://docs.google.com/forms/d/e/1FAIpQLSfkHcuiqXJDbhJWZNQKaKDWMmVPj-km8QwORc5tWWG7JhKRbw/viewform |

---

## 5. レスポンシブデザイン

ブレークポイント: `max-width: 768px`

- フォントサイズ縮小
- パディング調整
- 三角形ナビ → 縦並びに変更

---

## 6. SEO

```html
<meta name="description" content="...">
<meta property="og:title" content="...">
<meta name="twitter:card" content="summary_large_image">
```

---

## 7. パフォーマンス

- 初期表示: < 1秒
- 外部依存: なし
- 画像: なし（テキストベース）

---

## 8. 改訂履歴

| バージョン | 日付 | 変更内容 |
|-----------|------|---------|
| 1.0 | 2025-11-04 | 初版作成 |
| 2.0 | 2025-11-05 | ファイル名英語統一・GitHub Pages対応 |
| 3.0 | 2026-03-25 | index.htmlによろず相談AI・減災カレンダーカード追加。「ツールとリソース」セクション新設。「3つまとめて開く」削除。HDMG_DESIGN_SYSTEMカラー統一。 |

---

**お問い合わせ**: tbk_gensai_labo@tmhp.jp
