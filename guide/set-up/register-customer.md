# 顧客登録

## 1-1. 請求グループの作成

{% hint style="info" %}
請求グループとは請求書を発行する単位のRipple上での名称です。
{% endhint %}

まず、請求書を発行したい単位ごとに請求グループを作成する作業を行います。

* 顧客別
* 部署別
* 案件別　　等

\(Rippleは請求書を発行したい単位を１請求グループとし、各情報を記入します\)



左メニューの `アカウントとグループ` &gt;`請求グループ`から、画面右上の`請求グループの追加`をクリック。

Rippleの画面に従ってフィールド内に以下の情報をご入力ください。

<table>
  <thead>
    <tr>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
      <th style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;ID</td>
      <td style="text-align:left">&#x5FC5;&#x9808;</td>
      <td style="text-align:left">*&#x5909;&#x66F4;&#x4E0D;&#x53EF;</td>
      <td style="text-align:left">&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;&#x3092;&#x7BA1;&#x7406;&#x3059;&#x308B;&#x305F;&#x3081;&#x306E;&#x56FA;&#x6709;&#x306E;ID</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;&#x540D;</td>
      <td style="text-align:left">&#x5FC5;&#x9808;</td>
      <td style="text-align:left">&#x5909;&#x66F4;&#x53EF;</td>
      <td style="text-align:left">
        <p>&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;&#x3092;&#x7BA1;&#x7406;&#x3059;&#x308B;&#x305F;&#x3081;&#x306E;&#x540D;&#x79F0;&#x3002;</p>
        <p>&#x9867;&#x5BA2;&#x306B;&#x306F;&#x898B;&#x3048;&#x306A;&#x3044;&#x305F;&#x3081;&#x3001;</p>
        <p>&#x7BA1;&#x7406;&#x3057;&#x3084;&#x3059;&#x3044;&#x540D;&#x79F0;&#x3092;&#x3054;&#x767B;&#x9332;&#x304F;&#x3060;&#x3055;&#x3044;&#x3002;</p>
        <p>(&#x4F8B;&#xFF1A;&#x9867;&#x5BA2;&#x540D;&#x3001;&#x6848;&#x4EF6;&#x540D;&#x306A;&#x3069;)</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">&#x4F01;&#x696D;&#x540D;</td>
      <td style="text-align:left">&#x5FC5;&#x9808;</td>
      <td style="text-align:left">&#x5909;&#x66F4;&#x53EF;</td>
      <td style="text-align:left">&#x8ACB;&#x6C42;&#x66F8;&#x767A;&#x884C;&#x5148;&#x306E;&#x4F01;&#x696D;&#x540D;</td>
    </tr>
  </tbody>
</table>以下は任意項目です。

* 電話番号
* 郵便番号
* 住所
* 宛名
* 請求書タイトル
* 備考欄

　　　　　　　　　　　　　                            \*請求グループIDのみ、登録後の変更ができません。

## 1-2. 請求関連の諸条件を設定

請求書の値引きや手数料に関する計算を請求書単位で設定することが可能です。

[1-1.](https://app.gitbook.com/@mobingidocs/s/docs/~/edit/drafts/-Lgkj2JW-gQ_b7KZifbT/v/ripple/guide/set-up/register-customer#1-gurpuno)で作成した請求グループの `•••` &gt; `請求書設定の変更` をクリックし、請求関連の諸条件を設定します。

## 2. 請求グループにAWSアカウントを連結する

[1-1.](https://app.gitbook.com/@mobingidocs/s/docs/~/edit/drafts/-Lgkj2JW-gQ_b7KZifbT/v/ripple/guide/set-up/register-customer#1-gurpuno)で作成した請求グループにAWSのアカウントを紐づける作業を行います。

左メニューの`アカウントとグループ`&gt;`アカウント`から、画面右上の`アカウントの追加`をクリックし、フィールドに必要内容を記入し追加します。

Payerアカウントの利用料も請求書に含めたい場合はこのページで再度ご登録ください。

{% hint style="danger" %}
**既に登録済みのアカウントIDを重複登録することはできません。**
{% endhint %}



