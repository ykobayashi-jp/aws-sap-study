# aws-sap-study

![AWS SAP-C02](https://img.shields.io/badge/AWS-SAP--C02-232F3E?logo=amazonaws&logoColor=white)
![問題数](https://img.shields.io/badge/問題数-107問-blue)
![Vanilla JS](https://img.shields.io/badge/JS-Vanilla-F7DF1E?logo=javascript&logoColor=black)
![No build](https://img.shields.io/badge/build-none-lightgrey)
![License](https://img.shields.io/badge/license-MIT-green)

AWS Solutions Architect Professional (SAP-C02) の試験対策用 Web アプリです。  
問題演習・詳細解説・サービス比較表・チートシート・用語集をブラウザだけで完結させます。

---

## 📋 コンテンツ概要

### 問題演習 (`index.html`)

| 分野 | 問題数 | カバーするトピック |
|---|---|---|
| 設計 | 16問 | HA/DR・スケーラビリティ・マイクロサービス・サーバーレス・Well-Architected |
| セキュリティ | 14問 | IAM/SCP・KMS・Cognito・GuardDuty・インシデント対応・コンプライアンス |
| ネットワーク | 14問 | VPC・Direct Connect・Transit Gateway・Network Firewall・DNS・PrivateLink |
| コスト | 12問 | 購入オプション・S3ライフサイクル・Compute Optimizer・コスト可視化 |
| 移行 | 13問 | DMS/SCT・MGN・Snowball・7R戦略・Strangler Figパターン |
| コンテナ | 12問 | ECS・EKS・Fargate・IRSA・Cluster Autoscaler・Blue/Green |
| データ | 14問 | Kinesis・Athena・Redshift・DynamoDB Streams・OpenSearch・SageMaker |
| 監視 | 12問 | CloudWatch・X-Ray・AWS Config・Patch Manager・Session Manager |
| **合計** | **107問** | Medium 69問 / Hard 38問 |

各問題には **正解の理由・落とし穴・サービス比較表・キーワード** が付いています。

### 参考書 (`study.html`)

| セクション | 内容 |
|---|---|
| チートシート | 9カテゴリ・68サービスをカード形式で要点まとめ |
| サービス比較表 | DR戦略・RDS vs Aurora・SQS vs SNS vs EventBridge など5種 |
| 分野別ポイント | 試験で狙われるポイントと落とし穴を分野ごとに整理 |
| アーキテクチャ図解 | マルチリージョンDR・データパイプライン・ハイブリッド接続 |
| 用語集・略語 | RPO/RTO/CDC/IRSA など45語をリアルタイム検索 |

---

## ✨ Features

- **深掘り解説** — 正解の理由 + よくある落とし穴を毎問表示
- **サービス比較表** — 類似サービスの違いを問題ごとに整理
- **分野別フィルタ** — 苦手分野だけ絞って集中練習
- **スコア追跡** — 正答率・連続正解・分野別グラフ（結果画面）
- **ビルド不要** — ブラウザで開くだけ。npm install 不要
- **PC / スマホ対応** — スマホではボトムナビに切り替わる
- **ダークテーマ** — 目に優しい暗めのデザイン

> ⚠️ アイコンフォントを CDN から読み込むため、初回表示にネット接続が必要です。

---

## 🚀 Getting started

```bash
git clone https://github.com/yourname/aws-sap-study.git
cd aws-sap-study
open index.html     # macOS
# start index.html  # Windows
```

または [GitHub Pages](https://yourname.github.io/aws-sap-study/) でブラウザから直接アクセス。

---

## 🗂 Structure

```
aws-sap-study/
├── index.html    # 問題演習アプリ（107問収録）
├── study.html    # 参考書ページ（チートシート・比較表・図解・用語集）
└── README.md
```

問題データは `index.html` 内の `const QS = [...]` に直接記載しています。

---

## ➕ Adding questions

`index.html` 内の `const QS = [...]` に以下の形式でオブジェクトを追加してください。

```js
{
  domain: "セキュリティ",   // 下表の値を使用
  cat:    "IAM / SCP",      // バッジ表示用（自由記述）
  diff:   "Medium",         // "Easy" | "Medium" | "Hard"
  q:    "問題文...",
  opts: ["選択肢A", "選択肢B", "選択肢C", "選択肢D"],
  ans:  1,                  // 正解の選択肢インデックス（0始まり）
  why:  "正解の理由...",
  trap: "よくある落とし穴...",
  cmp: [                    // サービス比較表（省略可）
    { svc: "サービス名", feature: "特徴", rto: "RTO目安", cost: "低/中/高", note: "備考" }
  ],
  kws: ["キーワード1", "キーワード2"]
}
```

### domain に指定できる値

| 値 | カバーするトピック例 |
|---|---|
| `設計` | HA・DR・スケーラビリティ・サーバーレス・Well-Architected |
| `セキュリティ` | IAM・KMS・CloudHSM・GuardDuty・Cognito・Config |
| `ネットワーク` | VPC・Direct Connect・Transit Gateway・Network Firewall |
| `コスト` | 購入オプション・S3ライフサイクル・Compute Optimizer |
| `移行` | DMS・SCT・MGN・Snowball・7R・Migration Hub |
| `コンテナ` | ECS・EKS・Fargate・IRSA・Cluster Autoscaler |
| `データ` | Kinesis・Athena・Redshift・DynamoDB・OpenSearch・SageMaker |
| `監視` | CloudWatch・X-Ray・AWS Config・Systems Manager |

---

## 📄 License

MIT
