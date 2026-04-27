# 🌿 樹木医ツール — Arborist Certified Tools

> 樹木医（日本樹木医会認定）が監修した、無料の樹木管理Webツール集。  
> 病害虫の早期発見・剪定適期の判断・現地健全度調査をブラウザから即座に実行できます。

[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Tools](https://img.shields.io/badge/Tools-3-brightgreen)]()
[![Languages](https://img.shields.io/badge/HTML%20%2F%20CSS%20%2F%20JS-vanilla-blue)]()
[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-orange)]()

---

## 📋 ツール一覧

| ツール | ファイル | 概要 |
|---|---|---|
| 🦠 病害虫リスク診断 | `diagnosis.html` | 樹種・季節・症状からリスクと対処法を即表示 |
| 📅 剪定適期カレンダー | `pruning.html` | 15樹種×6目的の月別剪定適否をカラー表示 |
| 📋 樹木健全度チェックリスト | `checklist.html` | 32項目の現地調査シート・A〜Dランク自動算出 |

---

## 🚀 デモ

**[→ サイトを見る](https://arborist-tools.pages.dev)**  
*(Cloudflare Pages でホスティング)*

---

## 🏗 技術スタック

- **フロントエンド**: HTML / CSS / Vanilla JavaScript のみ
- **依存ライブラリ**: なし（外部フォントのみ Google Fonts）
- **ビルドツール**: 不要
- **ホスティング**: Cloudflare Pages / GitHub Pages（静的配信）

すべてのロジックはクライアントサイドで完結しており、サーバー・データベース不要です。

---

## 📁 ファイル構成

```
arborist-tools/
├── index.html        # トップページ（ツール一覧・FAQ・About）
├── diagnosis.html    # 病害虫リスク診断ツール
├── pruning.html      # 剪定適期カレンダー計算機
├── checklist.html    # 樹木健全度チェックリスト
├── privacy.html      # プライバシーポリシー（作成予定）
├── contact.html      # お問い合わせ（作成予定）
└── README.md
```

---

## 🌱 ローカルで動かす

ビルド不要です。クローン後にHTMLファイルをブラウザで開くだけで動作します。

```bash
git clone https://github.com/YOUR_USERNAME/arborist-tools.git
cd arborist-tools
# index.html をブラウザで開く
open index.html        # macOS
start index.html       # Windows
xdg-open index.html   # Linux
```

---

## 🤝 コントリビュート

**樹種の追加・診断データの拡充・UI改善など、どんな貢献も歓迎します。**

### コントリビュートの流れ

```bash
# 1. このリポジトリをFork
# 2. ブランチを作成
git checkout -b feature/add-zelkova-data

# 3. 変更をコミット
git commit -m "feat: ケヤキの病害虫データを追加"

# 4. Pushしてプルリクエストを作成
git push origin feature/add-zelkova-data
```

### 優先してほしいコントリビュート

- [ ] 対応樹種の拡充（現在15樹種）
- [ ] 病害虫データベースの精度向上
- [ ] 地域別（北海道・九州・沖縄等）の時期補正機能
- [ ] 英語対応（i18n）
- [ ] 診断結果のPDF出力機能
- [ ] スマートフォン向けPWA化

### データ構造（`diagnosis.html` の場合）

新しい樹種を追加する際は `diagnosisDB` オブジェクトに以下の形式で追記してください。

```javascript
// diagnosis.html 内の diagnosisDB に追記
zelkova: {
  "leaf-yellow,branch-dead": {
    risk: "high",                          // "high" | "mid" | "low"
    title: "ケヤキの診断結果",
    pests: [
      {
        name: "てんぐ巣病",
        desc: "糸状菌による感染。感染枝に多数の細枝が叢生する。"
      }
    ],
    actions: [
      "罹患枝を健全部から20cm以上下で切除",
      "切り口にトップジンMペーストを塗布"
    ],
    caution: "剪定は落葉期（冬季）に行うのが理想です。"
  }
}
```

---

## 🐛 バグ報告・機能要望

[Issues](../../issues) からお気軽にどうぞ。  
テンプレートを用意していますので、できるだけ詳しく記載いただけると助かります。

---

## 📜 ライセンス

[MIT License](LICENSE) — 商用・非商用問わず自由に使用・改変・再配布できます。  
ただし著作権表示は保持してください。

---

## 👤 監修・開発

- **樹木医監修**: 日本樹木医会認定 樹木医
- **開発**: [@YOUR_USERNAME](https://github.com/YOUR_USERNAME)

---

## 📊 ロードマップ

```
v1.0  ✅ 3ツール公開（診断・カレンダー・チェックリスト）
v1.1  🔲 プライバシーポリシー・お問い合わせページ追加
v1.2  🔲 対応樹種を30種へ拡充
v1.3  🔲 診断結果PDF出力
v2.0  🔲 PWA化（オフライン対応・現地でインターネット不要）
v2.1  🔲 英語対応
```
