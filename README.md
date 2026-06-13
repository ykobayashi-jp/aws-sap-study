# aws-sap-study

![AWS SAP-C02](https://img.shields.io/badge/AWS-SAP--C02-blue)
![Vanilla JS](https://img.shields.io/badge/JS-Vanilla-green)
![No build](https://img.shields.io/badge/build-none-lightgrey)
![License](https://img.shields.io/badge/license-MIT-blue)

AWS Solutions Architect Professional (SAP-C02) の試験対策用 Web アプリです。  
問題演習・詳細解説・サービス比較表をブラウザだけで完結させます。

## Features

- **深掘り解説** — 正解の理由 + よくある落とし穴を毎問表示
- **サービス比較表** — 類似サービスの違いを一覧で整理
- **分野別フィルタ** — 設計 / セキュリティ / ネットワーク / コスト / 移行 / コンテナ / データ / 監視
- **スコア追跡** — 正答率・連続正解・分野別グラフ（結果画面）
- **ビルド不要** — `index.html` をブラウザで開くだけ。依存ライブラリなし

## Getting started

```bash
git clone https://github.com/yourname/aws-sap-study.git
cd aws-sap-study
open index.html   # macOS — 問題演習
# start index.html  # Windows
```

- `index.html` — 問題演習アプリ。ブラウザで開くだけで動作します
- `study.html` — 参考書ページ。チートシート・比較表・図解・用語集

## Structure

```
aws-sap-study/
├── index.html    # 問題演習アプリ
├── study.html    # 参考書ページ（チートシート・比較表・図解・用語集）
└── README.md
```

問題データは `index.html` 内の `const QS = [...]` に直接記載しています。  
問題数が増えてきたら `questions/*.json` に分割して fetch で読み込む形に移行できます。

## Adding questions

`index.html` 内の `const QS = [...]` に以下の形式でオブジェクトを追加してください。

```js
{
  domain: "セキュリティ",       // 分野フィルタに使用（DOMAINS配列と一致させること）
  cat: "IAM / SCP",             // バッジ表示用
  diff: "難",                   // "易" | "普通" | "難"
  q: "問題文...",
  opts: ["選択肢A", "選択肢B", "選択肢C", "選択肢D"],
  ans: 0,                       // 正解インデックス（0始まり）
  why: "正解の理由...",
  trap: "よくある落とし穴...",
  cmp: [                        // サービス比較表（省略可）
    { svc: "サービス名", feature: "特徴・RPO目安", rto: "RTO目安", cost: "低/中/高", note: "備考" }
  ],
  kws: ["キーワード1", "キーワード2"]
}
```

### domain に指定できる値

| 値 | 内容 |
|---|---|
| `設計` | HA / DR / スケーラビリティ |
| `セキュリティ` | IAM / KMS / GuardDuty など |
| `ネットワーク` | VPC / Direct Connect / Transit Gateway |
| `コスト` | 購入オプション / コスト最適化 |
| `移行` | DMS / Migration Hub / Snowball |
| `コンテナ` | ECS / EKS / サーバーレス |
| `データ` | Kinesis / Athena / Redshift |
| `監視` | CloudTrail / CloudWatch / EventBridge |

## License

MIT
