# プロジェクト構造 / Project Structure

```
gensai-labo-knowledge/          # プロジェクトルート
│
├── README.md                   # プロジェクト概要・使い方
├── QUICKSTART.md               # 5分でデプロイできるガイド
├── DEPLOY.md                   # 詳細なデプロイ手順書
├── LICENSE.md                  # ライセンス情報
├── .gitignore                  # Git除外設定
├── index.html                  # ルート用リダイレクトページ
├── technical-specification-v2.md  # 技術仕様書
│
└── docs/                       # GitHub Pages公開フォルダ ★重要★
    ├── index.html             # メインポータルページ
    ├── philosophy.html        # 災害対応力向上研修 哲学五箇条
    ├── principles.html        # 訓練企画10原則
    └── movable-60-vs-perfect-100.html  # 動ける60点 > 動けない100点
```

## 📁 ファイル詳細

### ルートディレクトリ

| ファイル | 役割 | 重要度 |
|---------|------|--------|
| `README.md` | プロジェクトの説明、概要、使い方 | ⭐⭐⭐⭐⭐ |
| `QUICKSTART.md` | 5分でできる最速デプロイガイド | ⭐⭐⭐⭐ |
| `DEPLOY.md` | 詳細なデプロイ手順とトラブルシューティング | ⭐⭐⭐⭐ |
| `LICENSE.md` | コンテンツとコードのライセンス情報 | ⭐⭐⭐⭐⭐ |
| `.gitignore` | Gitで管理しないファイルの設定 | ⭐⭐⭐ |
| `index.html` | ルート用リダイレクトページ | ⭐⭐ |
| `technical-specification-v2.md` | 技術仕様書 | ⭐⭐⭐ |

### docs/ ディレクトリ（公開サイト）

| ファイル | 内容 | サイズ |
|---------|------|--------|
| `index.html` | ポータルページ | 14 KB |
| `philosophy.html` | 災害対応力向上研修 哲学五箇条 | 40 KB |
| `principles.html` | 訓練企画10原則 | 41 KB |
| `movable-60-vs-perfect-100.html` | 動ける60点 > 動けない100点 | 66 KB |

**合計サイズ**: 約161 KB（超軽量！）

## 🔧 GitHub Pages設定

GitHub Pagesで公開するには：

1. Settings → Pages
2. Source: `main` branch
3. **Folder: `/docs`** ← これが最重要！

`/docs` を指定することで、`docs/index.html` が公開サイトのトップページになります。

## 📊 ディレクトリの役割

### なぜ `docs/` を使うのか？

1. **GitHub Pages標準**: GitHub Pagesが推奨する構造
2. **分離**: ドキュメント（README等）と公開コンテンツを分離
3. **拡張性**: 将来的に `assets/`、`images/` など追加しやすい

### 将来的な拡張例

```
docs/
├── index.html
├── philosophy.html
├── principles.html
├── movable-60-vs-perfect-100.html
├── assets/              # 将来追加
│   ├── css/
│   ├── js/
│   └── images/
└── api/                 # 将来追加（APIドキュメント等）
```

## 🚀 デプロイフロー

```
1. ローカルで編集
   ↓
2. Git commit & push
   ↓
3. GitHub Actions（自動）
   ↓
4. GitHub Pagesに反映（3-5分）
   ↓
5. https://[ユーザー名].github.io/[リポジトリ名]/ で公開
```

## 📝 編集時の注意

### コンテンツを更新する場合
→ `docs/` 内のHTMLファイルを編集

### ドキュメントを更新する場合
→ ルートの `.md` ファイルを編集

### 新しいページを追加する場合
1. `docs/` に新しいHTMLファイルを作成
2. `docs/index.html` からリンク
3. Git commit & push

## 🔒 セキュリティ

- ✅ 静的サイト: サーバーサイド脆弱性なし
- ✅ HTTPS: 自動で有効
- ✅ 依存関係: なし（外部ライブラリ不使用）

## 📈 パフォーマンス

- **ロード時間**: < 1秒
- **サイズ**: 161 KB（超軽量）
- **外部リクエスト**: 0（完全スタンドアロン）

## 🔄 更新頻度の推奨

| 項目 | 頻度 |
|-----|------|
| コンテンツ（docs/内） | 必要に応じて |
| README.md | 四半期ごと |
| 技術仕様書 | 大きな変更時のみ |
| ライセンス | 変更なし |

## 📞 サポート

質問や問題があれば：
- 📧 Email: tbk_gensai_labo@tmhp.jp
- 🐛 GitHub Issues
- 📖 DEPLOY.md を参照

---

**バージョン**: 2.0  
**最終更新**: 2025年11月5日  
**構造設計**: 提案2（docs/フォルダ集約型）
