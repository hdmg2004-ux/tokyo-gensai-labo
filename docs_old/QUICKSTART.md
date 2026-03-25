# クイックスタートガイド

このガイドでは、最短5分でプロジェクトをGitHub Pagesで公開する方法を説明します。

## 🚀 最速デプロイ（5分）

### ステップ1: リポジトリを作成（1分）

1. [GitHub](https://github.com) にアクセス
2. 右上の「+」→「New repository」
3. リポジトリ名: `gensai-labo-knowledge`（または任意の名前）
4. Public を選択
5. 「Create repository」ボタンをクリック

### ステップ2: ファイルをアップロード（2分）

1. 作成したリポジトリページで「uploading an existing file」をクリック
2. 以下のファイル・フォルダを**すべて**ドラッグ&ドロップ:
   ```
   ✓ docs/ フォルダ（中の全ファイル含む）
   ✓ README.md
   ✓ LICENSE.md
   ✓ DEPLOY.md
   ✓ technical-specification-v2.md
   ✓ index.html
   ✓ .gitignore
   ```
3. Commit message: `Initial commit`
4. 「Commit changes」ボタンをクリック

### ステップ3: GitHub Pagesを有効化（2分）

1. リポジトリページの「Settings」タブ
2. 左メニュー「Pages」
3. Source設定:
   - Branch: `main` を選択
   - Folder: `/docs` を選択 ← **超重要！**
4. 「Save」ボタン
5. 数分待つ

### ステップ4: 確認

緑色のバーに表示されるURLにアクセス:
```
https://[あなたのユーザー名].github.io/[リポジトリ名]/
```

**完了！** 🎉

---

## 📝 README.mdの編集

公開後、README.mdを編集して実際の情報に更新してください：

1. リポジトリページで `README.md` をクリック
2. 鉛筆アイコン（Edit）をクリック
3. 以下を置き換え:
   ```
   [ユーザー名] → あなたのGitHubユーザー名
   [リポジトリ名] → 作成したリポジトリ名
   ```
4. 「Commit changes」

同様に `index.html` も編集してください。

---

## 🔧 トラブルシューティング

### 404エラーが出る

**確認事項**:
- Settings → Pages → Folder が `/docs` になっているか
- `docs/` フォルダに `index.html` があるか

**解決策**:
1. 再度 Folder を `/docs` に設定
2. 5分待つ
3. キャッシュクリア（Ctrl+Shift+R）

### リンクが動かない

**確認事項**:
- `docs/` フォルダに以下の4ファイルがあるか
  - index.html
  - philosophy.html
  - principles.html
  - movable-60-vs-perfect-100.html

### ページが表示されない

**待ち時間**:
- 初回デプロイ: 最大10分
- 更新: 3〜5分

**確認方法**:
リポジトリの「Actions」タブで Build状況を確認

---

## 💡 次のステップ

### カスタマイズ

1. `docs/index.html` を編集して組織名を変更
2. カラースキームを調整（CSS変数を編集）
3. Google Analytics を追加

### コンテンツ更新

```bash
# ローカルで編集後
git add docs/
git commit -m "Update content"
git push origin main
```

### 独自ドメイン

1. ドメインを取得
2. Settings → Pages → Custom domain に入力
3. DNS設定（CNAMEレコード）

詳細は `DEPLOY.md` を参照

---

## 📚 ドキュメント

- **README.md** - プロジェクト概要
- **DEPLOY.md** - 詳細なデプロイ手順
- **LICENSE.md** - ライセンス情報
- **technical-specification-v2.md** - 技術仕様

---

## 💬 サポート

困ったときは:
- 📧 Email: tbk_gensai_labo@tmhp.jp
- 📖 [GitHub Pages ドキュメント](https://docs.github.com/ja/pages)
- 🐛 [Issue を作成](../../issues)

---

**所要時間**: 5分  
**難易度**: ⭐☆☆☆☆（初心者向け）  
**最終更新**: 2025年11月5日
