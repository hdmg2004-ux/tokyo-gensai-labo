# 東京医療減災Labo 実践知の体系 - 技術仕様書

**作成日**: 2025年11月4日  
**バージョン**: 2.0  
**最終更新**: 2025年11月5日

---

## 1. 概要

東京医療減災Laboの3つの資料（哲学五箇条、訓練企画10原則、動ける60点>動けない100点）とインデックスページを、縦スクロール形式・目次機能付き・レスポンシブ対応のWebページとして実装。

### 作成ファイル
- `index.html` - トップページ（3つの資料へのポータル）
- `philosophy.html` - 災害対応力向上研修 哲学五箇条
- `principles.html` - 訓練企画10原則
- `movable-60-vs-perfect-100.html` - 動ける60点 > 動けない100点

---

## 2. 技術スタック

### フロントエンド
- **HTML5** - セマンティックマークアップ
- **CSS3** - カスタムスタイリング（フレームワーク不使用）
- **Vanilla JavaScript** - 軽量なインタラクション実装

### フレームワーク・ライブラリ
- **使用していません**
  - React、Vue.js等のJavaScriptフレームワークは不使用
  - Bootstrap、Tailwind CSS等のCSSフレームワークは不使用
  - jQuery等のライブラリも不使用

### 理由
- ページの軽量性を最優先
- 依存関係なしで長期的なメンテナンス性を確保
- 静的ファイルとして配信可能（サーバーレス対応）

---

## 3. デザイン仕様

### レイアウト方式
**縦スクロール + アンカーリンク方式**

従来のページめくり方式から変更：
- 各セクションに `id` 属性を付与
- スムーススクロール（`scroll-behavior: smooth`）
- アンカーリンクによる直接ジャンプ

### カラースキーム
```css
/* プライマリカラー */
--primary-blue: #2a5298
--primary-gradient: linear-gradient(135deg, #1e3c72 0%, #2a5298 100%)

/* アクセントカラー */
--accent-red: #dc143c  /* 「災」の強調 */
--accent-gold: #ffd700 /* 重要箇所の強調 */

/* 背景 */
--bg-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%)
--bg-light: #fafafa
--bg-white: #ffffff
```

### タイポグラフィ
```css
/* フォントファミリー */
font-family: 'Hiragino Kaku Gothic ProN', 'Hiragino Sans', 
             'Yu Gothic', 'Meiryo', sans-serif;

/* 見出し用（明朝体） */
font-family: 'Hiragino Mincho ProN', 'Yu Mincho', 
             'MS Mincho', serif;

/* サイズ */
h1: 2.5em ~ 2.8em
h2: 2.2em
h3: 1.8em
body: 1.1em
```

---

## 4. レスポンシブデザイン

### ブレークポイント
```css
/* モバイル */
@media (max-width: 768px) {
  /* フォントサイズ縮小 */
  /* パディング調整 */
  /* 目次メニューの全画面表示 */
}
```

### 対応デバイス
- **PC**: 900px以上のコンテナ幅
- **タブレット**: 768px以下で最適化
- **スマートフォン**: 最小320pxまで対応

### レスポンシブ対応内容
1. フォントサイズの流動的調整（clamp関数使用）
2. パディング・マージンの縮小
3. 目次メニューの位置調整（PC: 右下、モバイル: 全画面）
4. タッチデバイス最適化

---

## 5. 目次機能の実装

### UI構成
```
[目次ボタン] (右下固定)
    ↓ クリック
[目次メニュー] (スライドイン表示)
    - 表紙
    - セクション1
    - セクション2
    ...
```

### JavaScript実装
```javascript
// 目次の開閉
function toggleTOC() {
    const menu = document.getElementById('tocMenu');
    menu.classList.toggle('show');
}

// 目次を閉じる
function closeTOC() {
    const menu = document.getElementById('tocMenu');
    menu.classList.remove('show');
}

// 目次外クリックで自動的に閉じる
document.addEventListener('click', function(e) {
    const menu = document.getElementById('tocMenu');
    const button = document.querySelector('.toc-button');
    
    if (!menu || !button) return;
    
    if (menu.classList.contains('show') && 
        !menu.contains(e.target) && 
        e.target !== button) {
        menu.classList.remove('show');
    }
});
```

### アニメーション
```css
/* 目次メニューのスライドイン */
.toc-menu {
    opacity: 0;
    transform: translateY(20px);
    transition: all 0.3s;
}

.toc-menu.show {
    opacity: 1;
    transform: translateY(0);
}
```

---

## 6. SEO最適化

### メタタグ実装
```html
<!-- 基本SEO -->
<meta name="description" content="...">
<meta name="keywords" content="...">
<meta name="author" content="中島康">
<meta name="robots" content="index, follow">

<!-- OGP (Open Graph Protocol) -->
<meta property="og:title" content="...">
<meta property="og:description" content="...">
<meta property="og:type" content="website">
<meta property="og:site_name" content="東京医療減災Labo">
<meta property="og:locale" content="ja_JP">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="...">
<meta name="twitter:description" content="...">
```

### セマンティックHTML
- `<header>`, `<nav>`, `<main>`, `<section>`, `<article>` 等を適切に使用
- 見出しタグ（h1~h6）の階層構造を適切に保持
- アクセシビリティ向上のためのaria属性（必要に応じて追加可能）

---

## 7. パフォーマンス

### ファイルサイズ
| ファイル | サイズ | 備考 |
|---------|--------|------|
| philosophy.html | 約30KB | 圧縮前 |
| principles.html | 約32KB | 圧縮前 |
| movable-60-vs-perfect-100.html | 約45KB | 圧縮前 |
| index.html | 約15KB | 圧縮前 |

### ロード時間
- **初期表示**: < 1秒（通常回線）
- **外部依存**: なし（完全スタンドアロン）
- **画像**: なし（テキストベース）

### 最適化手法
1. **インラインCSS**: 外部スタイルシートなし
2. **インラインJavaScript**: 外部JSファイルなし
3. **フォント**: システムフォント使用（Webフォント不使用）
4. **キャッシュ**: 静的ファイルとして長期キャッシュ可能

---

## 8. ブラウザ互換性

### 対応ブラウザ
- **Chrome**: 最新版 + 過去2バージョン
- **Firefox**: 最新版 + 過去2バージョン
- **Safari**: 最新版 + 過去2バージョン
- **Edge**: 最新版 + 過去2バージョン

### 使用CSS機能
- CSS Grid: 部分的に使用（フォールバック対応）
- Flexbox: 多用（IE11以降対応）
- CSS Variables: 使用（一部）
- Scroll Behavior Smooth: 使用（非対応ブラウザでも動作）

### 使用JavaScript機能
- ES6: 一部使用（Arrow Function, const/let等）
- DOM API: 標準APIのみ
- イベントリスナー: addEventListener使用

---

## 9. アクセシビリティ

### 現在の対応
- セマンティックHTML構造
- 適切な見出し階層
- 十分なコントラスト比
- タッチターゲットサイズ（最小44x44px）

### 今後の改善余地
- WAI-ARIA属性の追加
- キーボードナビゲーション強化
- スクリーンリーダー対応の検証
- Focus管理の改善

---

## 10. デプロイメント

### 推奨ホスティング
1. **Netlify** - 静的サイトホスティング（無料枠で十分）
2. **GitHub Pages** - Gitリポジトリと連携
3. **Cloudflare Pages** - CDN統合
4. **Amazon S3 + CloudFront** - エンタープライズ向け

### ファイル構成
```
/
├── index.html
├── philosophy.html
├── principles.html
└── movable-60-vs-perfect-100.html
```

### デプロイ手順（Netlify例）
1. Netlifyアカウント作成
2. 「New site from Git」選択
3. リポジトリ接続
4. Build settings:
   - Build command: (なし)
   - Publish directory: `/`
5. Deploy

### GitHub対応（v2.0での変更）
**ファイル名の英語化**: GitHubでのファイル管理とURLの可読性向上のため、主要HTMLファイル名を英語表記に統一しました。

**変更内容**:
- `災害対応力向上研修_哲学五箇条.html` → `philosophy.html`
- `訓練企画10原則_v2.html` → `principles.html`
- `movable-60-vs-perfect-100.html` → 変更なし（既に英語表記）
- `index.html` → 変更なし

**互換性**: 旧ファイル名は削除せず、リダイレクトまたは両方保持を推奨します。

### カスタムドメイン設定
- `gensai-labo.jp` 等のドメイン取得
- DNS設定（A/CNAMEレコード）
- SSL証明書自動発行（Let's Encrypt）

---

## 11. 内部リンク構造

### ナビゲーション設計
```
index.html (ポータル)
    ├── philosophy.html (理念編)
    ├── principles.html (実践編)
    └── movable-60-vs-perfect-100.html (戦略編)
         ↑                 ↑                ↑
         └─────────────────┴────────────────┘
              相互リンク（奥付セクション）
```

### リンク実装
- **絶対パス**: 使用していない
- **相対パス**: `./philosophy.html` 形式
- **アンカーリンク**: `#section-id` 形式

---

## 12. 今後の拡張可能性

### Phase 1（現状）
✅ 静的HTMLページ
✅ 縦スクロール形式
✅ 目次機能
✅ レスポンシブ対応

### Phase 2（次期バージョン案）
- [ ] アクセス解析（Google Analytics / Plausible）
- [ ] 検索機能（ページ内検索）
- [ ] 印刷最適化CSS
- [ ] ダークモード対応

### Phase 3（将来構想）
- [ ] インタラクティブ診断ツール
- [ ] PDFダウンロード機能
- [ ] 多言語対応（英語・中国語）
- [ ] コメント・フィードバック機能

---

## 13. 保守・運用

### バージョン管理
- **推奨**: Git + GitHub
- **ブランチ戦略**: 
  - `main`: 本番環境
  - `develop`: 開発環境
  - `feature/*`: 機能追加

### 更新頻度
- **コンテンツ更新**: 四半期ごと
- **技術的改善**: 年1回
- **セキュリティパッチ**: 必要に応じて

### バックアップ
- GitHubリポジトリが自動バックアップとして機能
- 追加で外部ストレージ（Google Drive / Dropbox）推奨

---

## 14. ライセンス・著作権

### コンテンツ
- **ライセンス**: CC BY-NC-SA 4.0
- **著作権者**: 中島康 / 東京医療減災Labo
- **商用利用**: 不可
- **改変・再配布**: 不可

### コード
- **ライセンス**: MIT License（推奨）
- **オープンソース化**: 可能

---

## 15. 連絡先・サポート

### お問い合わせ
- **Email**: tbk_gensai_labo@tmhp.jp
- **組織**: 東京医療減災Labo (HDMG2004)

### 技術サポート
- 技術的な質問: 上記メールアドレスまで
- バグ報告: GitHub Issues（リポジトリ公開後）

---

## 付録A: コードスニペット集

### スムーススクロールの実装
```css
html {
    scroll-behavior: smooth;
}
```

### 目次ボタンのホバーエフェクト
```css
.toc-button {
    transition: all 0.3s;
}

.toc-button:hover {
    background: #ffd700;
    color: #333;
    transform: translateY(-3px);
}
```

### レスポンシブフォントサイズ
```css
.principle-title {
    font-size: clamp(1.8em, 4.5vw, 2.8em);
}
```

---

## 付録B: 既知の制限事項

### 技術的制限
1. **オフライン対応**: 現状未対応（PWA化で対応可能）
2. **印刷**: 最適化なし（print.css追加で改善可能）
3. **検索**: ページ内検索のみ（サイト内横断検索は未実装）

### ブラウザ別問題
- **IE11**: scroll-behavior非対応（ポリフィル可）
- **Safari旧版**: 一部CSS Grid非対応（フォールバック済み）

---

## 改訂履歴

| バージョン | 日付 | 変更内容 | 担当 |
|-----------|------|---------|------|
| 1.0 | 2025-11-04 | 初版作成 | Claude |
| 2.0 | 2025-11-05 | ファイル名を英語表記に統一（GitHub対応）<br>- `災害対応力向上研修_哲学五箇条.html` → `philosophy.html`<br>- `訓練企画10原則_v2.html` → `principles.html`<br>- `index.html`内のリンクを全て新ファイル名に更新 | Claude |

---

**文書作成**: Claude (Anthropic)  
**レビュー**: 東京医療減災Labo  
**最終更新**: 2025年11月5日
