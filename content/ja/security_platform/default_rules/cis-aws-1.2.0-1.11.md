---
aliases:
  - /ja/v5j-jba-9tg
  - /ja/security_monitoring/default_rules/v5j-jba-9tg
  - /ja/security_monitoring/default_rules/cis-aws-1.2.0-1.11
cloud: AWS
disable_edit: true
integration_id: amazon-iam
kind: documentation
rule_category:
  - クラウドコンフィギュレーション
scope: iam
security: コンプライアンス
source: iam
title: IAM ポリシーは、90 日以内にパスワードを期限切れにするように設定されています
type: security_rules
---
## 説明

IAM パスワードポリシーでは、指定された日数後にパスワードをローテーションまたは期限切れにする必要がある場合があります。パスワードポリシーは、90 日以内にパスワードの有効期限が切れる必要があります。

## 根拠

パスワードの有効期間を短縮すると、ブルートフォースログインの試行に対するアカウントの復元力が向上します。さらに、パスワードの定期的な変更を要求することは、知らないうちにパスワードが盗まれたり侵害されたりした場合に役立ちます。これは、ソフトウェアの脆弱性が原因でシステムが危険にさらされている場合、または内部の脅威がある場合に発生する可能性があります。特定の企業および政府の Web フィルターまたはプロキシサーバーには、暗号化されている場合でもトラフィックを傍受して記録する機能があります。多くの人が、仕事、電子メール、個人などの多くのシステムで同じパスワードを使用しています。 侵害されたエンドユーザーワークステーションには、キーストロークロガーが搭載されている可能性があります。

## 修復

コンソールの修復手順については、[CIS AWS Foundations ベンチマークコントロールのドキュメント][1]を参照してください。

## 影響

なし

## デフォルト値

なし

## リファレンス

1. CCE-78909-9

## CIS Controls

16 アカウントの監視と制御

[1]: https://docs.aws.amazon.com/securityhub/latest/userguide/securityhub-cis-controls.html#securityhub-cis-controls-1.3