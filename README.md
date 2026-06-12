# aws-sap-study

![AWS SAP-C02](https://img.shields.io/badge/AWS-SAP--C02-blue) ![Vanilla JS](https://img.shields.io/badge/JS-Vanilla-green) ![No build](https://img.shields.io/badge/build-none-lightgrey)

AWS Solutions Architect Professional (SAP-C02) の試験対策用 Web アプリです。
問題演習・詳細解説・サービス比較表・チートシートをブラウザだけで完結させます。

## Features

- 深掘り解説 — 正解の理由 + よくある落とし穴を毎問表示
- サービス比較表 — 類似サービスの違いを一覧で整理
- 分野別フィルタ — 苦手分野を絞って集中練習
- スコア追跡 — 正答率・連続正解・分野別グラフ
- ビルド不要 — HTML 1ファイルをブラウザで開くだけ
- 全12分野対応 — 設計・セキュリティ・DR・移行など

## Getting started

```bash
git clone https://github.com/yourname/aws-sap-study.git
cd aws-sap-study
open index.html   # or just double-click
```

依存ライブラリなし。`index.html` をブラウザで開くだけで動作します。

## Structure

```
├── index.html      # アプリ本体（全コード同梱）
├── README.md
└── questions/      # 問題データ（JSON、任意で分割可）
```

## Adding questions

`index.html` 内の `const QS = [...]` に以下の形式でオブジェクトを追加してください。

```js
{
  domain: "セキュリティ",
  cat: "IAM / SCP",
  diff: "難",
  q: "問題文...",
  opts: ["A", "B", "C", "D"],
  ans: 0,           // 0-indexed
  why: "正解の理由...",
  trap: "落とし穴...",
  cmp: [{ svc, rpo, rto, cost, note }],
  kws: ["キーワード1", "キーワード2"]
}
```

## License

MIT
