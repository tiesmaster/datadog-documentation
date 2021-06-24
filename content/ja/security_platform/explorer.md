---
title: セキュリティシグナルエクスプローラー
kind: documentation
description: すべてのセキュリティシグナルを検索し、セキュリティ分析を実施
aliases:
  - /ja/security_monitoring/explorer/
further_reading:
  - link: 'https://www.datadoghq.com/blog/announcing-security-monitoring/'
    tag: ブログ
    text: セキュリティモニタリングの詳細
  - link: /security_monitoring/detection_rules/
    tag: Documentation
    text: セキュリティルールの条件付きロジックについて
---
## 概要

[セキュリティシグナルエクスプローラー][1]から、セキュリティシグナルを相互に関連付けて優先順位を付けます。このページからセキュリティ監視ダッシュボードにアクセスすることもできます。

このビューで、以下を行うことができます。

* [セキュリティシグナルについて](#explore-your-security-signals)
* [セキュリティシグナルの調査](#inspect-a-security-signal)
* [セキュリティシグナル分析の可視化](#visualize-your-security-signals-analytics)

## セキュリティシグナルの探索

セキュリティシグナルの検索結果が、セキュリティシグナルテーブルに表示されます。

{{< img src="security_platform/security_monitoring/explorer/ss_table.png" alt="セキュリティシグナルテーブル"  >}}

テーブルのコンテンツを、使用可能なファセットのリストで絞り込むことができます。右上に表示される **Options** ボタンを使用して、セキュリティシグナルテーブルのコンテンツを要件や好みに応じて構成できます。

## セキュリティシグナルの検査

セキュリティシグナルをクリックすると、セキュリティシグナルパネルが開いて詳細が表示されます。

{{< img src="security_platform/security_monitoring/explorer/signal_1.png" alt="セキュリティシグナル"  >}}

問題を選別する際に最初に必要になる情報が、セキュリティシグナルパネルの最上部に表示されます。これらの情報から、シグナルの重要度や生成日時を判断したり、規則の設定にアクセスしたり、シグナルをチームメイトとすばやく共有したりできます。

FIRST SEEN と LAST SEEN の日時は更新され、過去にないデータが新しく表示されているのか、それとも攻撃が続いているのかを確認できます。また、何を基準にグループ化しているかも、このセクションに表示されます。この例では、`usr.name` でグループ化するように規則が構成されています。その下には、規則に設定されたタグが表示されています。

{{< img src="security_platform/security_monitoring/explorer/signal_2.png" alt="セキュリティシグナル"  >}}

アクティビティをよりよく理解するために、セキュリティシグナルパネルは、シグナルをトリガーするすべてのログのタグと属性を要約するため、ログエクスプローラーにピボットすることなくトラブルシューティングを行うことができます。たとえば、ユーザーアカウントにログインしようとしている IP のリスト、または認証サービスを実行している AWS アカウントとアベイラビリティーゾーンを一目で判断できます。

シグナルの概要の下には、シグナルに関連する詳細情報が表示されたタブがあります。

- `Message` は、シグナルをレビューする人がシグナルの目的と応答方法を理解するのに役立つように、ルールで構成されたテキストを表示します。

- `Event Attributes` は、セキュリティシグナルの優先順位付けとフィルタリングを行うときに役立ちます。たとえば、ユーザーまたはエンティティがその無害な動作の一部としてセキュリティルールをトリガーした、またはコンプライアンス制御がすべての環境に適用されるべきではないと判断する場合があります。Event Attributes タブの任意の属性をクリックしてドロップダウンメニューを生成し、**Never trigger signals for **`<value>`**** を選択して、セキュリティシグナルエクスプローラー内に表示されるものを微調整します。このメニューから、属性に関連するログをフィルタリングまたは表示することもできます。

  {{< img src="security_platform/security_monitoring/explorer/never_trigger_signal_option.png" alt="設定値に対してシグナルをトリガーしないオプション" >}}

- `Samples` には、シグナルがトリガーされた理由に関するコンテキストを提供するログサンプルのリストが含まれています。完全なログを表示するには、サンプルのいずれかをクリックしてください。

- `Related Issues` には、シグナルのトリアージを支援するために同じグループ化値を含む他のシグナルのリストが含まれています。

### 異常検知

レビューしているセキュリティシグナルが異常検知メソッドにより生成されている場合、異常はグラフで可視化されます。グラフ右側の境界ボックスには、異常が検知された場所が表示されます。

  {{< img src="security_platform/security_monitoring/explorer/anomaly-detection.png" alt="異常検知のグラフ" >}}

## セキュリティシグナル分析を視覚化する

ページの左上隅にある _Signal Mode_ ボタンをクリックすると、セキュリティシグナルテーブルとセキュリティシグナル分析の間でモードが切り替わります。

{{< img src="security_platform/security_monitoring/explorer/visualize_analytics1.png" alt="分析の可視化"  >}}

セキュリティ規則エンジンによってセキュリティシグナルが生成されたら、セキュリティシグナルのクエリをグラフ化して、最大値、最小値、パーセンタイル、ユニーク数などを確認できます。

すべてのグラフ作成オプションについては、[ログのグラフ作成ガイド][2]を参照してください。

## その他の参考資料

{{< partial name="whats-next/whats-next.html" >}}


[1]: https://app.datadoghq.com/security
[2]: /ja/logs/explorer/analytics/?tab=timeseries