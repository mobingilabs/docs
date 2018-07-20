# レポートとCSVの見方

* このページではダッシュボードのレポートとダウンロードしたCSVを照らし合わせ、各項目について説明しています。

  レポートとCSVで同義で違う単語や略称で表示されている項目があります。

  下の図で同じ色で囲われている部分が同様の項目となります。

![](../.gitbook/assets/csv_report.png)

1. AccountID: AWSのアカウントID
   * レポートはアカウント単位での表示・ダウンロードなので1つのCSVにつき1つのIDのみ表示されます。
2. ServiceCode: AWSの各サービス名
   * Elastic Cpmpute Cloudなど、尚、CSVでは `Elastic Compute Cloud` は `AmazonEC2` 、`Simple Storage Service` は `AmazonS3`などと略称で表示されます。
3. CostBeforeTax: 税抜きの月次利用額
   * レポートは小数点以下第2位まで表示されます。この例ではレポート上は `$21.18` CSVでは `21.18966134` で一致しています。
4. Region: リージョン
   * この例ではダッシュボードは `Asia Pacific(Tokyo)` と表示されており、CSVだと`ap-northeast-1` となります。どちらとも東京リージョンを指しています。
5. UsageQuantity: 使用量
   * この例ではレポート上は `1,394.05` CSVでは `1,394.056667` で一致しています。
6. InstanceType: インスタンスタイプ
   * この例ではレポート、CSVともに `t2.micro` で一致しています。
7. ItemDescription: 詳細
   * この例ではレポート、CSVともに `$0.0152 per on-demand t2.micro EC2 instance hour (or partial hour)` で一致しています。

