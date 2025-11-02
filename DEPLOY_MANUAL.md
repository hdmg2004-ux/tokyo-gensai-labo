# GitHub Pages 手動アップロード手順書

## 前提条件
- GitHubアカウント（未作成の場合: https://github.com/signup）
- 準備完了ファイル: 全7ファイル（HTML 4つ + 補助ファイル 3つ）

---

## Step 1: リポジトリ作成（所要時間: 2分）

1. **GitHub にログイン**
   - https://github.com にアクセス

2. **新規リポジトリ作成**
   - 右上の「+」→「New repository」をクリック
   
3. **設定項目を入力**
   ```
   Repository name: tokyo-gensai-labo
   Description: 災害対応力向上研修の実践知体系
   Public: ✅ チェック（必須）
   Initialize with README: □ チェックしない（既にREADMEあり）
   ```

4. **「Create repository」をクリック**

---

## Step 2: ファイルアップロード（所要時間: 5分）

1. **リポジトリページで「uploading an existing file」をクリック**
   - または「Add file」→「Upload files」

2. **7つのファイルをドラッグ&ドロップ**
   ```
   ✅ index.html
   ✅ philosophy.html
   ✅ principles.html
   ✅ movable-60-vs-perfect-100.html
   ✅ README.md
   ✅ LICENSE
   ✅ .gitignore
   ```

3. **コミットメッセージを入力**
   ```
   Commit message: Initial commit - 実践知の体系を公開
   ```

4. **「Commit changes」をクリック**

---

## Step 3: GitHub Pages 有効化（所要時間: 2分）

1. **リポジトリの「Settings」タブをクリック**

2. **左サイドバーの「Pages」をクリック**

3. **Source設定**
   ```
   Branch: main
   Folder: / (root)
   ```

4. **「Save」をクリック**

5. **2-3分待つと公開完了**
   - 画面上部に公開URLが表示されます
   - `https://[username].github.io/tokyo-gensai-labo/`

---

## Step 4: 動作確認（所要時間: 3分）

1. **公開URLにアクセス**
   - `https://[username].github.io/tokyo-gensai-labo/`

2. **4つのリンクをテスト**
   - ✅ 哲学五箇条
   - ✅ 訓練企画10原則
   - ✅ 動ける60点 > 動けない100点
   - ✅ 各ページからの戻りリンク

3. **モバイル表示確認（任意）**
   - スマートフォンでアクセステスト

---

## トラブルシューティング

### 🔴 404 Not Found が表示される
**原因**: GitHub Pages の反映待ち  
**対処**: 5分程度待ってから再アクセス

### 🔴 ファイルが見つからない
**原因**: ファイル名の大文字小文字が違う  
**対処**: ファイル名を確認（すべて小文字推奨）

### 🔴 リンクが切れている
**原因**: 相対パスが間違っている  
**対処**: 本パッケージは検証済みのため、再アップロードを試す

---

## 公開後のURL

**メインページ:**
```
https://[username].github.io/tokyo-gensai-labo/
```

**個別ページ:**
```
https://[username].github.io/tokyo-gensai-labo/philosophy.html
https://[username].github.io/tokyo-gensai-labo/principles.html
https://[username].github.io/tokyo-gensai-labo/movable-60-vs-perfect-100.html
```

---

## カスタムドメインの設定（任意）

独自ドメイン（例: www.gensai-labo.jp）をお持ちの場合:

1. **Settings > Pages > Custom domain**
2. **ドメインを入力**
3. **DNSレコードを設定**（詳細はGitHub公式ドキュメント参照）

---

## 更新方法

ファイルを修正した場合:

1. GitHubリポジトリの該当ファイルをクリック
2. 鉛筆アイコン（Edit）をクリック
3. 内容を修正
4. 「Commit changes」
5. 1-2分後に反映

---

## サポート

**問題が解決しない場合:**
- GitHub公式ドキュメント: https://docs.github.com/pages
- 東京医療減災Labo: tbk_gensai_labo@tmhp.jp

---

**作成日:** 2025年11月2日  
**対象リポジトリ:** tokyo-gensai-labo
