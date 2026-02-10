# GitHub Pagesデプロイ手順

このドキュメントでは、本プロジェクトをGitHub Pagesで公開する手順を説明します。

## 前提条件

- GitHubアカウントを持っていること
- GitまたはGitHub Desktopがインストールされていること

## 手順

### 1. リポジトリの作成

1. GitHubにログイン
2. 右上の「+」→「New repository」をクリック
3. リポジトリ名を入力（例: `gensai-labo-knowledge`）
4. Publicを選択
5. 「Create repository」をクリック

### 2. ファイルのアップロード

#### 方法A: コマンドライン（推奨）

```bash
# プロジェクトフォルダに移動
cd /path/to/project

# Gitリポジトリを初期化
git init

# ファイルを追加
git add .

# コミット
git commit -m "Initial commit: Tokyo Medical Disaster Reduction Lab Knowledge System"

# リモートリポジトリを追加
git remote add origin https://github.com/[ユーザー名]/[リポジトリ名].git

# プッシュ
git branch -M main
git push -u origin main
```

#### 方法B: GitHub Webインターフェース

1. リポジトリページで「uploading an existing file」をクリック
2. すべてのファイルをドラッグ&ドロップ
3. Commit messageを入力
4. 「Commit changes」をクリック

#### 方法C: GitHub Desktop

1. GitHub Desktopを開く
2. 「File」→「Add local repository」
3. プロジェクトフォルダを選択
4. 「Publish repository」をクリック

### 3. GitHub Pagesの有効化

1. リポジトリページの「Settings」タブをクリック
2. 左メニューから「Pages」を選択
3. **Source**セクションで設定:
   - Branch: `main`
   - Folder: `/docs` ← **重要**
4. 「Save」をクリック

### 4. 公開URLの確認

数分後、ページ上部に以下のようなメッセージが表示されます：

```
Your site is live at https://[ユーザー名].github.io/[リポジトリ名]/
```

このURLが公開サイトのアドレスです。

## トラブルシューティング

### 404エラーが表示される

**原因**: GitHub Pagesの設定が `/docs` になっていない

**解決策**:
1. Settings → Pages → Folder が `/docs` になっているか確認
2. 再度「Save」をクリック
3. 数分待って再アクセス

### ページが更新されない

**原因**: ブラウザキャッシュ、またはGitHub側の反映待ち

**解決策**:
1. ブラウザで Ctrl+Shift+R（強制リロード）
2. 5〜10分待ってから再アクセス
3. Actions タブで Build状況を確認

### リンクが切れている

**原因**: 相対パスの問題

**解決策**:
- すべてのHTMLファイルが `docs/` フォルダ内にあることを確認
- `index.html` から他のファイルへのリンクが正しいか確認

## カスタムドメインの設定（オプション）

独自ドメイン（例: `gensai-labo.jp`）を使いたい場合：

1. ドメインを取得（お名前.com、ムームードメインなど）
2. GitHub Pages設定で「Custom domain」に入力
3. DNS設定でCNAMEレコードを追加:
   ```
   Type: CNAME
   Name: www
   Value: [ユーザー名].github.io
   ```
4. 「Enforce HTTPS」を有効化

## 更新方法

### コンテンツを更新した場合

```bash
# 変更をステージング
git add docs/

# コミット
git commit -m "Update content: [変更内容]"

# プッシュ
git push origin main
```

数分後、自動的に公開サイトに反映されます。

## README.mdの更新

README.md内の以下の箇所を実際の情報に置き換えてください：

- `[ユーザー名]` → あなたのGitHubユーザー名
- `[リポジトリ名]` → 作成したリポジトリ名

## セキュリティ

- ✅ Static HTML: サーバー側の脆弱性なし
- ✅ HTTPS: GitHub Pagesは自動的にHTTPS対応
- ✅ メールアドレス: スパム対策としてJavaScriptエンコード検討可

## パフォーマンス最適化

現在の構成で十分ですが、さらに最適化する場合：

1. **画像圧縮**: 将来的に画像を追加する場合、WebP形式を推奨
2. **HTMLミニファイ**: 本番環境では圧縮版を使用
3. **CDN**: 大規模アクセスが予想される場合、Cloudflare併用

## モニタリング（オプション）

### Google Analytics
```html
<!-- docs/index.html の </head> 前に追加 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

### Plausible Analytics（プライバシー重視）
```html
<script defer data-domain="yourdomain.com" src="https://plausible.io/js/script.js"></script>
```

## サポート

問題が発生した場合:
1. [GitHub Pages ドキュメント](https://docs.github.com/ja/pages)
2. [Issue] タブで報告
3. tbk_gensai_labo@tmhp.jp に連絡

---

**文書作成日**: 2025年11月5日  
**対象バージョン**: v2.0
