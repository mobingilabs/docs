# 原価データを出力する

本機能はCost and Usage Reportのデータを元に、AWSからRippleユーザーへの請求金額情報（原価）をCSV形式で出力する機能です。

{% hint style="info" %}
**CSVをダウンロードできるタイミング**  
→ Invoice IDが確定したタイミング。月内に複数のInvoice IDが存在する場合、確定した内容から出力が可能となります。
{% endhint %}

## 操作方法 <a id="how-to-use"></a>

Ripple左メニューの`ツール`から`原価のデータの出力(.csv)`をクリックし、年月を選択する。

1. **ドルベースのCSVをダウンロードする場合** 右上の`原価データの一括出力`をクリックし、`米ドルで出力`ボタンからCSVをダウンロードする。 \*ドルのCSVでは小数点以下の丸め処理は行いません。 
2. **円ベースのCSVをダウンロードする場合** 表示されているInvoice ID横のチェックボックスを選択し、`為替レートの登録`ボタンを押す。全てのInvoice IDに対して為替レートを登録したのち、`原価データの一括出力`ボタンから小数点の丸め処理を選択、`日本円で出力`ボタンをクリックする。

## CSVの項目について <a id="csv-data"></a>

利用料はアカウント単位で一行、その他の費用及びInvoice IDが異なるものに関してはアイテムごとに一行出力されます。

出力したCSVには以下の項目が含まれます。

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x9805;&#x76EE;</th>
      <th style="text-align:left">&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;ID</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">BillingGroupID</td>
      <td style="text-align:left">&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;&#x306E;ID</td>
    </tr>
    <tr>
      <td style="text-align:left">BillingGroupName</td>
      <td style="text-align:left">&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;&#x540D;</td>
    </tr>
    <tr>
      <td style="text-align:left">Project Code</td>
      <td style="text-align:left">&#x30D7;&#x30ED;&#x30B8;&#x30A7;&#x30AF;&#x30C8;&#x30B3;&#x30FC;&#x30C9;
        <br
        />&#xFF08;&#x8A2D;&#x5B9A;&#x3057;&#x3066;&#x3044;&#x306A;&#x3044;&#x5834;&#x5408;&#x306F;&#x7A7A;&#x6B04;&#xFF09;</td>
    </tr>
    <tr>
      <td style="text-align:left">Payer accountID</td>
      <td style="text-align:left">&#x305D;&#x306E;&#x30A2;&#x30AB;&#x30A6;&#x30F3;&#x30C8;&#x304C;&#x7D10;&#x3065;&#x304F;Payer&#x30A2;&#x30AB;&#x30A6;&#x30F3;&#x30C8;&#x306E;ID</td>
    </tr>
    <tr>
      <td style="text-align:left">Vendor</td>
      <td style="text-align:left">&#x30AF;&#x30E9;&#x30A6;&#x30C9;&#x306E;&#x7A2E;&#x985E;</td>
    </tr>
    <tr>
      <td style="text-align:left">Invoice ID</td>
      <td style="text-align:left">
        <p>AWS&#x306B;&#x3088;&#x308A;&#x8ACB;&#x6C42;&#x66F8;&#x5358;&#x4F4D;&#x3067;&#x8A2D;&#x5B9A;&#x3055;&#x308C;&#x3066;&#x3044;&#x308B;ID</p>
        <p>CUR&#x4E0A;&#x306E;&#x300C;bill/InvoiceId&#x300D;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">CustomerID</td>
      <td style="text-align:left">AWS&#x30A2;&#x30AB;&#x30A6;&#x30F3;&#x30C8;ID</td>
    </tr>
    <tr>
      <td style="text-align:left">Type</td>
      <td style="text-align:left">
        <p>&#x5229;&#x7528;&#x6599; (Usage)&#x3001;Fee (&#x8CFC;&#x5165;&#x8CBB;&#x7528;)&#x3001;&#x8FD4;&#x91D1;
          (Refund)&#x3001;&#x30AF;&#x30EC;&#x30B8;&#x30C3;&#x30C8; (Credit) &#x3092;&#x533A;&#x5225;&#x3059;&#x308B;&#x9805;&#x76EE;</p>
        <p>CUR&#x4E0A;&#x306E;&#x300C;lineItem/LineItemType&#x300D;&#x304C;&#x57FA;&#x6E96;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Description</td>
      <td style="text-align:left">
        <p>Type&#x304C;Fee, Refund, Credit&#x306E;&#x5834;&#x5408;&#x306E;&#x30A2;&#x30A4;&#x30C6;&#x30E0;&#x306E;&#x8AAC;&#x660E;&#x3002;</p>
        <p>CUR&#x4E0A;&#x306E;&#x300C;lineItem/LineItemDescription&#x300D;</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Charge</td>
      <td style="text-align:left">&#x7A0E;&#x629C;&#x304D;&#x306E;&#x91D1;&#x984D;</td>
    </tr>
    <tr>
      <td style="text-align:left">Tax</td>
      <td style="text-align:left">&#x7A0E;&#x984D;</td>
    </tr>
    <tr>
      <td style="text-align:left">Total</td>
      <td style="text-align:left">&#x7A0E;&#x8FBC;&#x91D1;&#x984D;&#xFF08;Charge + Tax&#xFF09;</td>
    </tr>
    <tr>
      <td style="text-align:left">Exchange rate</td>
      <td style="text-align:left">Ripple&#x4E0A;&#x3067;&#x767B;&#x9332;&#x3055;&#x308C;&#x305F;&#x70BA;&#x66FF;&#x30EC;&#x30FC;&#x30C8;</td>
    </tr>
  </tbody>
</table>

