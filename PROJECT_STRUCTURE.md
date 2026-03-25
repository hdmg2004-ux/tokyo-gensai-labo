# プロジェクト構造 / Project Structure

```
gensai-labo-knowledge/
│
├── README.md                           # プロジェクト概要・使い方
├── LICENSE.md                          # ライセンス情報
├── technical-specification-v2.md       # 技術仕様書
├── .gitignore
│
└── docs/                               # GitHub Pages公開フォルダ ★重要★
    ├── index.html                     # メインポータルページ
    ├── philosophy.html                # 災害対応力向上研修 哲学五箇条
    ├── principles.html                # 訓練企画10原則
    └── movable-60-vs-perfect-100.html # 動ける60点 > 動けない100点
```

## 📁 ファイル詳細

### docs/ ディレクトリ（公開サイト）

| ファイル | 内容 |
|---------|------|
| `index.html` | ポータルページ。5つのカードで構成 |
| `philosophy.html` | 災害対応力向上研修 哲学五箇条 |
| `principles.html` | 訓練企画10原則 |
| `movable-60-vs-perfect-100.html` | 動ける60点 > 動けない100点 |

### index.htmlの構成（v3.0）

**課題別ガイド**（白背景・3カード）
1. 哲学五箇条（理念編）→ philosophy.html
2. 訓練企画10原則（実践編）→ principles.html
3. 動ける60点（戦略編）→ movable-60-vs-perfect-100.html

**ツールとリソース**（薄グレー背景・2カード）
4. よろず相談AI → https://yorozu-chat.vercel.app/
5. 減災カレンダーHDMG → Googleフォーム申込

---

## 🔧 GitHub Pages設定

1. Settings → Pages
2. Source: `main` branch
3. **Folder: `/docs`**

## 🚀 デプロイフロー

```
ローカルで編集
　↓
Git commit & push
　↓
GitHub Pages自動反映（数分）
　↓
https://hdmg2004-ux.github.io/tokyo-gensai-labo/
```

## 📝 編集時の注意

- コンテンツ更新 → `docs/` 内のHTMLファイルを編集
- 新ページ追加 → `docs/` にHTML作成 → `docs/index.html` からリンク

---

**バージョン**: 3.0
**最終更新**: 2026年3月25日
