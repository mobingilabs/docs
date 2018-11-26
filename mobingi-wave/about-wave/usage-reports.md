# レポート

レポートでは、AWSの各サービスの利用状況を詳細に可視化できます。

![](../../.gitbook/assets/screen-shot-2018-11-26-at-16.29.09.png)

{% hint style="info" %}
日次データ（デイリー）について

更新タイミング：毎日  
データ鮮度：約二日前のデータ
{% endhint %}

{% hint style="info" %}
月次データ（マンスリー）について

更新タイミング：毎月5日頃  
データ鮮度：先月以前の利用分を表示
{% endhint %}

アカウント、グループ、タグ、の3つの単位からデータを閲覧できます。  
それぞれの特徴は以下の通りです。

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left">説明</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">アカウント</td>
      <td style="text-align:left">
        <p>保有するアカウントごとの詳細な利用金額を把握できます。
          <br />アカウントごとに毎日、毎月の予算を設定できます。予算を超えた場合、EmailまたはSlackにて通知が受け取れます。</p>
        <p>歯車マークをクリックすることで、<a href="https://docs.mobingi.com/v/wave/mobingi-wave/a-lump-sum">AWSからの一時金</a>を確認できます。</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">グループ</td>
      <td style="text-align:left">複数のアカウントをグルーピングすることで、任意のまとまりでの利用金額を把握できます。
        <br />まずは<code>&#x30B0;&#x30EB;&#x30FC;&#x30D7; &#x306E;&#x4F5C;&#x6210;</code>から、グループを作成しましょう。</td>
    </tr>
    <tr>
      <td style="text-align:left">タグ</td>
      <td style="text-align:left">タグとは、AWSの各リソースにKey、Valueの形式で付与することができるラベルです。
        <br />AWSで利用されているタグごとの詳細な利用金額を把握できます。タグ機能の設定方法は、<a href="https://docs.mobingi.com/v/wave/mobingi-wave/tag-report">タグ機能の有効化</a>をご覧ください。</td>
    </tr>
  </tbody>
</table>### グラフ

Mobingi Waveのスマートなグラフは、AWSのサービスごとに使用状況を可視化します。

サービス単位ではなく、全サービスの合計を見たい場合は`トータル表示`のチェックボックスにチェックを入れてください。

フィルターを活用すれば、自分が見たいデータだけをグラフに表示できます。デフォルトでは、利用されている上位10個が選択されている状態です。

![](../../.gitbook/assets/screen-shot-2018-11-26-at-15.44.35%20%282%29.png)

### 月別およびプロダクト別の利用レポート

![](../../.gitbook/assets/screen-shot-2018-11-26-at-16.27.17.png)

グラフの下には、プロダクト別の詳細な利用レポートが表示されます。詳しくは[明細の確認方法](https://docs.mobingi.com/v/wave/mobingi-wave/detail-check)をご覧ください。

アカウントとタグのみ、データをCSV形式でダウンロードすることが可能です。データの見方については、[レポートとCSVの見方](https://docs.mobingi.com/v/wave/mobingi-wave/report-csv)をご覧ください。

