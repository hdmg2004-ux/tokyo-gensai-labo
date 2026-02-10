# 医療訓練ポータル デザインシステム仕様書

**バージョン**: 1.0  
**最終更新**: 2026年2月10日  
**用途**: 新規プロジェクトや既存システムの改善における統一的なデザイン基準

---

## 目次

1. [デザイン理念](#デザイン理念)
2. [カラーパレット](#カラーパレット)
3. [タイポグラフィ](#タイポグラフィ)
4. [スペーシング](#スペーシング)
5. [コンポーネント](#コンポーネント)
6. [レイアウトパターン](#レイアウトパターン)
7. [レスポンシブデザイン](#レスポンシブデザイン)
8. [アクセシビリティ](#アクセシビリティ)
9. [実装ガイド](#実装ガイド)

---

## デザイン理念

### コアバリュー

1. **プロフェッショナルで信頼できる** - 医療関係者が安心して使える
2. **シンプルで分かりやすい** - 多忙な医療従事者でも直感的に操作できる
3. **アクセシブル** - あらゆるユーザーが利用可能
4. **一貫性** - 全てのページで統一された体験

### デザイン原則

- **最小限の認知負荷**: 余計な装飾を排除し、必要な情報のみを提示
- **明確なアクション**: ボタンやリンクは視覚的に明確
- **適切なフィードバック**: ユーザーの操作に対して即座に反応
- **エラー予防**: 間違いを起こしにくいUI設計

---

## カラーパレット

### ブランドカラー

**プライマリカラー: Kakitsubata（燕子花色）**

```css
/* ブランドカラー（燕子花色） */
--primary: #3e62ad;
--primary-hover: #2d4a8c;
--primary-light: #5c7fc4;
--primary-lighter: #e8edf7;
```

**使用例**:
- メインボタン
- ヘッダー・ナビゲーション
- 重要なリンク
- アクティブ状態

### セマンティックカラー

**成功（Success）**
```css
--success: #22c55e;
--success-bg: #dcfce7;
--success-border: #86efac;
--success-text: #166534;
```

**警告（Warning）**
```css
--warning: #f59e0b;
--warning-bg: #fef3c7;
--warning-border: #fcd34d;
--warning-text: #92400e;
```

**危険（Danger）**
```css
--danger: #ef4444;
--danger-bg: #fee2e2;
--danger-border: #fca5a5;
--danger-text: #991b1b;
```

**情報（Info）**
```css
--info: #3b82f6;
--info-bg: #dbeafe;
--info-border: #93c5fd;
--info-text: #1e40af;
```

### ニュートラルカラー

```css
/* グレースケール */
--gray-50: #f9fafb;
--gray-100: #f3f4f6;
--gray-200: #e5e7eb;
--gray-300: #d1d5db;
--gray-400: #9ca3af;
--gray-500: #6b7280;
--gray-600: #4b5563;
--gray-700: #374151;
--gray-800: #1f2937;
--gray-900: #111827;

/* テキスト */
--text-primary: #111827;
--text-secondary: #6b7280;
--text-tertiary: #9ca3af;
--text-inverse: #ffffff;

/* 背景 */
--bg-primary: #ffffff;
--bg-secondary: #f9fafb;
--bg-tertiary: #f3f4f6;

/* ボーダー */
--border-default: #e5e7eb;
--border-focus: #3e62ad;
```

### 状態管理用カラー（定員管理）

```css
/* 空き状況バッジ */
--status-available: #22c55e;      /* 緑: 70%以上空き */
--status-limited: #eab308;        /* 黄: 30-70%空き */
--status-nearly-full: #f97316;    /* オレンジ: 30%未満空き */
--status-full: #ef4444;           /* 赤: 満員 */
```

**使用ルール**:
| 空き率 | カラー変数 | 背景色 | テキスト色 | 用途 |
|--------|-----------|--------|-----------|------|
| 70%以上 | `status-available` | `bg-green-100` | `text-green-800` | 余裕あり |
| 30-70% | `status-limited` | `bg-yellow-100` | `text-yellow-800` | 残りわずか |
| 30%未満 | `status-nearly-full` | `bg-orange-100` | `text-orange-800` | 満員間近 |
| 0% | `status-full` | `bg-red-100` | `text-red-800` | 満員 |

---

## タイポグラフィ

### フォントファミリー

```css
/* システムフォントスタック（高速・ネイティブ） */
--font-sans: -apple-system, BlinkMacSystemFont, "Segoe UI", 
             "Noto Sans JP", "Yu Gothic UI", "Hiragino Sans", 
             sans-serif;

--font-mono: "SF Mono", Monaco, Consolas, "Courier New", monospace;
```

### フォントサイズ

```css
/* テキストサイズ */
--text-xs: 0.75rem;     /* 12px */
--text-sm: 0.875rem;    /* 14px */
--text-base: 1rem;      /* 16px */
--text-lg: 1.125rem;    /* 18px */
--text-xl: 1.25rem;     /* 20px */
--text-2xl: 1.5rem;     /* 24px */
--text-3xl: 1.875rem;   /* 30px */
--text-4xl: 2.25rem;    /* 36px */
```

**使用ガイドライン**:
| サイズ | 用途 | 例 |
|--------|------|-----|
| `text-xs` | 補足テキスト、バッジ | 申込締切日、ステータス |
| `text-sm` | 本文（小）、ラベル | フォーム項目、説明文 |
| `text-base` | 本文（標準） | 通常の段落テキスト |
| `text-lg` | 本文（大）、強調 | リード文、重要な情報 |
| `text-xl` | セクションタイトル | カードタイトル |
| `text-2xl` | ページタイトル | 訓練名 |
| `text-3xl` | メインタイトル | ページヘッダー |
| `text-4xl` | ヒーローセクション | トップページ見出し |

### フォントウェイト

```css
--font-normal: 400;
--font-medium: 500;
--font-semibold: 600;
--font-bold: 700;
```

**使用ガイドライン**:
- **Normal (400)**: 本文テキスト
- **Medium (500)**: ラベル、小見出し
- **Semibold (600)**: ボタンテキスト、強調
- **Bold (700)**: 見出し、アラート

### 行間（Line Height）

```css
--leading-tight: 1.25;    /* 見出し用 */
--leading-normal: 1.5;    /* 本文用 */
--leading-relaxed: 1.75;  /* 読みやすさ重視 */
```

---

## スペーシング

### スペーシングスケール

```css
/* Tailwind標準スケール（4px基準） */
--space-0: 0;
--space-1: 0.25rem;   /* 4px */
--space-2: 0.5rem;    /* 8px */
--space-3: 0.75rem;   /* 12px */
--space-4: 1rem;      /* 16px */
--space-5: 1.25rem;   /* 20px */
--space-6: 1.5rem;    /* 24px */
--space-8: 2rem;      /* 32px */
--space-10: 2.5rem;   /* 40px */
--space-12: 3rem;     /* 48px */
--space-16: 4rem;     /* 64px */
```

### レイアウトスペーシング

**コンテナ内のスペース**:
```css
/* ページコンテナ */
.container-padding {
  padding-left: 1rem;   /* sm: 16px */
  padding-right: 1rem;
}

@media (min-width: 768px) {
  .container-padding {
    padding-left: 2rem;  /* md: 32px */
    padding-right: 2rem;
  }
}
```

**セクション間のスペース**:
- セクション間: `space-y-8` (32px)
- カード間: `space-y-4` (16px)
- フォーム要素間: `space-y-3` (12px)

---

## コンポーネント

### ボタン

#### プライマリボタン

```tsx
// 実装例（shadcn/ui）
<button className="
  inline-flex items-center justify-center 
  rounded-md text-sm font-semibold 
  bg-[#3e62ad] text-white 
  hover:bg-[#2d4a8c] 
  focus:outline-none focus:ring-2 focus:ring-[#3e62ad] focus:ring-offset-2
  disabled:opacity-50 disabled:cursor-not-allowed
  px-4 py-2
  transition-colors duration-200
">
  申込する
</button>
```

**Tailwindクラス構成**:
```
bg-[#3e62ad]          // プライマリカラー
hover:bg-[#2d4a8c]    // ホバー時の濃い色
text-white            // 白文字
rounded-md            // 中程度の角丸
px-4 py-2             // パディング
font-semibold         // セミボールドフォント
transition-colors     // スムーズな色変化
focus:ring-2          // フォーカスリング
disabled:opacity-50   // 無効時の透明度
```

#### セカンダリボタン

```tsx
<button className="
  inline-flex items-center justify-center
  rounded-md text-sm font-semibold
  bg-white text-gray-700 
  border border-gray-300
  hover:bg-gray-50
  focus:outline-none focus:ring-2 focus:ring-[#3e62ad] focus:ring-offset-2
  px-4 py-2
">
  キャンセル
</button>
```

#### 危険ボタン（削除など）

```tsx
<button className="
  inline-flex items-center justify-center
  rounded-md text-sm font-semibold
  bg-red-600 text-white
  hover:bg-red-700
  focus:outline-none focus:ring-2 focus:ring-red-500 focus:ring-offset-2
  px-4 py-2
">
  削除
</button>
```

#### ボタンサイズバリエーション

```tsx
// 小サイズ
<button className="px-3 py-1.5 text-xs">小</button>

// 標準サイズ
<button className="px-4 py-2 text-sm">標準</button>

// 大サイズ
<button className="px-6 py-3 text-base">大</button>
```

### カード

```tsx
<div className="
  bg-white 
  border border-gray-200 
  rounded-lg 
  shadow-sm
  p-6
  hover:shadow-md
  transition-shadow duration-200
">
  {/* カードコンテンツ */}
</div>
```

**構成要素**:
- **背景**: `bg-white`
- **ボーダー**: `border border-gray-200`
- **角丸**: `rounded-lg`
- **影**: `shadow-sm`, ホバー時 `shadow-md`
- **パディング**: `p-6` (24px)

### バッジ（ステータス表示）

```tsx
// 成功バッジ（緑）
<span className="
  inline-flex items-center 
  px-2.5 py-0.5 
  rounded-full 
  text-xs font-medium
  bg-green-100 text-green-800
">
  余裕あり
</span>

// 警告バッジ（黄）
<span className="
  inline-flex items-center 
  px-2.5 py-0.5 
  rounded-full 
  text-xs font-medium
  bg-yellow-100 text-yellow-800
">
  残りわずか
</span>

// 危険バッジ（赤）
<span className="
  inline-flex items-center 
  px-2.5 py-0.5 
  rounded-full 
  text-xs font-medium
  bg-red-100 text-red-800
">
  満員
</span>
```

### フォーム要素

#### テキストインプット

```tsx
<input 
  type="text"
  className="
    block w-full 
    rounded-md 
    border border-gray-300
    px-3 py-2
    text-sm
    placeholder:text-gray-400
    focus:outline-none focus:ring-2 focus:ring-[#3e62ad] focus:border-transparent
    disabled:bg-gray-100 disabled:cursor-not-allowed
  "
  placeholder="氏名を入力"
/>
```

#### セレクトボックス

```tsx
<select className="
  block w-full 
  rounded-md 
  border border-gray-300
  px-3 py-2
  text-sm
  focus:outline-none focus:ring-2 focus:ring-[#3e62ad] focus:border-transparent
">
  <option>選択してください</option>
  <option>医師</option>
  <option>看護師</option>
</select>
```

#### テキストエリア

```tsx
<textarea 
  className="
    block w-full 
    rounded-md 
    border border-gray-300
    px-3 py-2
    text-sm
    placeholder:text-gray-400
    focus:outline-none focus:ring-2 focus:ring-[#3e62ad] focus:border-transparent
  "
  rows={4}
  placeholder="参加希望理由を入力"
/>
```

#### ラベル

```tsx
<label className="
  block 
  text-sm font-medium 
  text-gray-700 
  mb-1
">
  氏名 <span className="text-red-500">*</span>
</label>
```

### アラート

```tsx
// 成功メッセージ
<div className="
  p-4 
  rounded-md 
  bg-green-50 
  border border-green-200
">
  <p className="text-sm text-green-800">
    ✓ 申込が完了しました
  </p>
</div>

// エラーメッセージ
<div className="
  p-4 
  rounded-md 
  bg-red-50 
  border border-red-200
">
  <p className="text-sm text-red-800">
    ✕ エラーが発生しました
  </p>
</div>

// 情報メッセージ
<div className="
  p-4 
  rounded-md 
  bg-blue-50 
  border border-blue-200
">
  <p className="text-sm text-blue-800">
    ℹ 重要なお知らせ
  </p>
</div>
```

### テーブル

```tsx
<table className="min-w-full divide-y divide-gray-200">
  <thead className="bg-gray-50">
    <tr>
      <th className="
        px-6 py-3 
        text-left text-xs font-medium 
        text-gray-500 uppercase tracking-wider
      ">
        訓練名
      </th>
      {/* 他のヘッダー */}
    </tr>
  </thead>
  <tbody className="bg-white divide-y divide-gray-200">
    <tr className="hover:bg-gray-50">
      <td className="px-6 py-4 whitespace-nowrap text-sm text-gray-900">
        救急医療訓練
      </td>
      {/* 他のセル */}
    </tr>
  </tbody>
</table>
```

---

## レイアウトパターン

### ページレイアウト

```tsx
<div className="min-h-screen bg-gray-50">
  {/* ヘッダー */}
  <header className="bg-white border-b border-gray-200">
    <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4">
      {/* ナビゲーション */}
    </div>
  </header>

  {/* メインコンテンツ */}
  <main className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-8">
    {/* ページコンテンツ */}
  </main>

  {/* フッター */}
  <footer className="bg-white border-t border-gray-200 mt-auto">
    <div className="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-4">
      {/* フッター内容 */}
    </div>
  </footer>
</div>
```

### カードグリッド

```tsx
<div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
  {items.map(item => (
    <div key={item.id} className="bg-white rounded-lg border border-gray-200 p-6">
      {/* カード内容 */}
    </div>
  ))}
</div>
```

### フォームレイアウト

```tsx
<form className="space-y-6">
  {/* フォームグループ */}
  <div>
    <label className="block text-sm font-medium text-gray-700 mb-1">
      氏名 <span className="text-red-500">*</span>
    </label>
    <input 
      type="text" 
      className="block w-full rounded-md border border-gray-300 px-3 py-2"
    />
  </div>

  {/* ボタングループ */}
  <div className="flex gap-3">
    <button type="submit" className="flex-1 bg-[#3e62ad] text-white px-4 py-2 rounded-md">
      送信
    </button>
    <button type="button" className="px-4 py-2 border border-gray-300 rounded-md">
      キャンセル
    </button>
  </div>
</form>
```

---

## レスポンシブデザイン

### ブレークポイント

```css
/* Tailwind標準ブレークポイント */
sm: 640px   /* スマートフォン（横） */
md: 768px   /* タブレット */
lg: 1024px  /* ノートPC */
xl: 1280px  /* デスクトップ */
2xl: 1536px /* 大画面 */
```

### レスポンシブパターン

#### コンテナ幅

```tsx
<div className="
  w-full 
  max-w-7xl 
  mx-auto 
  px-4 sm:px-6 lg:px-8
">
  {/* コンテンツ */}
</div>
```

#### グリッドレスポンス

```tsx
<div className="
  grid 
  grid-cols-1 
  sm:grid-cols-2 
  lg:grid-cols-3 
  gap-4 sm:gap-6
">
  {/* グリッドアイテム */}
</div>
```

#### テキストサイズ

```tsx
<h1 className="
  text-2xl sm:text-3xl lg:text-4xl 
  font-bold
">
  見出し
</h1>
```

#### スペーシング

```tsx
<div className="
  py-4 sm:py-6 lg:py-8
  space-y-4 sm:space-y-6
">
  {/* コンテンツ */}
</div>
```

### モバイルファースト設計

**原則**: デフォルトはモバイル向けのスタイルを定義し、大画面用に拡張

```tsx
// ✅ 良い例（モバイルファースト）
<div className="text-sm md:text-base lg:text-lg">

// ❌ 悪い例（デスクトップファースト）
<div className="text-lg md:text-base sm:text-sm">
```

---

## アクセシビリティ

### キーボードナビゲーション

**必須要件**:
- すべてのインタラクティブ要素がTabキーで到達可能
- フォーカス状態が視覚的に明確
- Enterキー/Spaceキーで操作可能

```tsx
// フォーカス可視化
<button className="
  focus:outline-none 
  focus:ring-2 
  focus:ring-[#3e62ad] 
  focus:ring-offset-2
">
```

### ARIAラベル

```tsx
// ボタンのラベル
<button aria-label="訓練に申し込む">
  申込
</button>

// 必須項目の表示
<input 
  aria-required="true"
  aria-label="氏名（必須）"
/>

// エラーメッセージとの関連付け
<input 
  aria-invalid="true"
  aria-describedby="email-error"
/>
<p id="email-error" className="text-red-600 text-sm">
  メールアドレスの形式が正しくありません
</p>
```

### カラーコントラスト

**WCAG 2.1 AA基準**:
- 通常テキスト: 4.5:1以上
- 大きいテキスト（18pt以上）: 3:1以上

**検証済みの組み合わせ**:
- `#3e62ad`（プライマリ） on `#ffffff`（白） ✓ 合格
- `#111827`（テキスト） on `#ffffff`（白） ✓ 合格
- `#6b7280`（セカンダリテキスト） on `#ffffff`（白） ✓ 合格

### スクリーンリーダー対応

```tsx
// 装飾的な要素を隠す
<div aria-hidden="true">
  {/* アイコンなど */}
</div>

// ライブリージョン（動的コンテンツ）
<div aria-live="polite" aria-atomic="true">
  申込が完了しました
</div>
```

---

## 実装ガイド

### shadcn/uiのセットアップ

**1. Tailwind CSSの設定**

```js
// tailwind.config.ts
module.exports = {
  content: [
    './app/**/*.{js,ts,jsx,tsx,mdx}',
    './components/**/*.{js,ts,jsx,tsx,mdx}',
  ],
  theme: {
    extend: {
      colors: {
        primary: {
          DEFAULT: '#3e62ad',
          hover: '#2d4a8c',
          light: '#5c7fc4',
          lighter: '#e8edf7',
        },
      },
    },
  },
}
```

**2. グローバルCSSの定義**

```css
/* app/globals.css */
@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  :root {
    --primary: #3e62ad;
    --primary-hover: #2d4a8c;
  }
  
  * {
    @apply border-border;
  }
  
  body {
    @apply bg-gray-50 text-gray-900;
  }
}
```

**3. shadcn/uiコンポーネントの追加**

```bash
# ボタンコンポーネントを追加
npx shadcn-ui@latest add button

# カードコンポーネントを追加
npx shadcn-ui@latest add card

# フォームコンポーネントを追加
npx shadcn-ui@latest add form
```

### コンポーネントのカスタマイズ

```tsx
// components/ui/button.tsx
import { cn } from "@/lib/utils"

export function Button({ className, ...props }) {
  return (
    <button
      className={cn(
        "inline-flex items-center justify-center",
        "rounded-md text-sm font-semibold",
        "bg-[#3e62ad] text-white",
        "hover:bg-[#2d4a8c]",
        "focus:ring-2 focus:ring-[#3e62ad]",
        "disabled:opacity-50",
        "px-4 py-2",
        "transition-colors",
        className
      )}
      {...props}
    />
  )
}
```

### 定員バッジの実装例

```tsx
// components/AvailabilityBadge.tsx
type AvailabilityBadgeProps = {
  available: number
  capacity: number
}

export function AvailabilityBadge({ available, capacity }: AvailabilityBadgeProps) {
  const rate = capacity > 0 ? available / capacity : 0
  
  const getStyle = () => {
    if (rate >= 0.7) return {
      bg: 'bg-green-100',
      text: 'text-green-800',
      label: '余裕あり'
    }
    if (rate >= 0.3) return {
      bg: 'bg-yellow-100',
      text: 'text-yellow-800',
      label: '残りわずか'
    }
    if (rate > 0) return {
      bg: 'bg-orange-100',
      text: 'text-orange-800',
      label: '満員間近'
    }
    return {
      bg: 'bg-red-100',
      text: 'text-red-800',
      label: '満員'
    }
  }
  
  const style = getStyle()
  
  return (
    <span className={`
      inline-flex items-center 
      px-2.5 py-0.5 
      rounded-full 
      text-xs font-medium
      ${style.bg} ${style.text}
    `}>
      {style.label} ({available}/{capacity})
    </span>
  )
}
```

### ダークモード対応（オプション）

```tsx
// ダークモード切り替え可能なコンポーネント
<div className="
  bg-white dark:bg-gray-800 
  text-gray-900 dark:text-gray-100
  border-gray-200 dark:border-gray-700
">
```

**注意**: 医療システムでは可読性が最優先のため、通常はライトモードのみで十分です。

---

## チェックリスト

### 新規コンポーネント作成時

- [ ] プライマリカラー `#3e62ad` を使用
- [ ] フォーカス状態が視覚的に明確
- [ ] レスポンシブデザイン対応（sm/md/lg）
- [ ] 適切なARIA属性を設定
- [ ] カラーコントラストが4.5:1以上
- [ ] ホバー・アクティブ状態の定義
- [ ] 無効状態（disabled）のスタイル
- [ ] トランジション効果（200ms推奨）

### ページ実装時

- [ ] ページタイトル（h1）が明確
- [ ] 一貫したスペーシング（space-y-6など）
- [ ] モバイルで横スクロールが発生しない
- [ ] タブレットでレイアウトが崩れない
- [ ] デスクトップで適切な最大幅設定（max-w-7xl）
- [ ] ローディング状態の表示
- [ ] エラー状態の表示
- [ ] 成功メッセージの表示

---

## 参考リソース

### 公式ドキュメント
- [Tailwind CSS](https://tailwindcss.com/docs)
- [shadcn/ui](https://ui.shadcn.com/)
- [Next.js](https://nextjs.org/docs)

### アクセシビリティ
- [WCAG 2.1ガイドライン](https://www.w3.org/WAI/WCAG21/quickref/)
- [MDN: ARIA](https://developer.mozilla.org/ja/docs/Web/Accessibility/ARIA)

### デザインシステム参考例
- [Material Design](https://material.io/design)
- [Apple Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines/)
- [Atlassian Design System](https://atlassian.design/)

---

## バージョン履歴

| バージョン | 日付 | 変更内容 |
|-----------|------|---------|
| 1.0 | 2026-02-10 | 初版リリース |

---

**作成**: Claude + ユーザー  
**ライセンス**: MIT  
**お問い合わせ**: tbk_gensai_labo@tmhp.jp
