---
description: 請求書を発行するフローについて説明しています。
---

# 請求書を発行する

[※ 請求書発行する前に、請求データ確定のご連絡と集計作業が必要です。](https://docs.mobingi.com/~/drafts/-LI4AaN4Frv--_hbAXgG/primary/v/ripple/mobingi-ripple/mobingi-ripple-gai-yao#dashboard)

## 1. Rippleで請求書を発行する

![](../.gitbook/assets/dashboard.png)

1. 請求対象の利用月を選択する。
2. 請求グループ毎に "Make Invoice" をクリック。

![](../.gitbook/assets/discount_detail.png)



これらの値は請求グループに事前に設定することができます。 事前設定内容を、請求書発行時に都度上書きすることが可能です。

* 支払タイプ
* 割引率
* 消費税率
* サポートビジネス費用
* 代行手数料
  * パーセント
  * 固定費
* 為替レート
* クーポン割引

           ※「請求書一括作成」の場合は、これらの項目を事前に設定する必要があります

![](../.gitbook/assets/click_invoice.png)

請求グループIDをクリックすることで、作成された請求書（THML）を確認できます。

![](../.gitbook/assets/invoices.png)

* このページを印刷することで請求書としてご利用いただくことが可能です。
* 一度作成した請求書はRipple内で保存されます。
  * 請求グループIDをクリックすると閲覧できます。
* 請求書のフォーマットは随時増やしていく予定です。

## 2. CSVデータをエクスポートする

![](../.gitbook/assets/csv_invoice.png)



1. 請求対象の利用月を選択する。
2. "請求書一括作成" をクリック。 ※ この操作により、「請求グループ毎の請求書（PDF）」と「すべての請求グループの請求データを網羅したCSVファイル」が作成されます。
3. "CSVダウンロード" をクリック。

### CSVデータのフォーマット：アカウント単位

![1&#x30A2;&#x30AB;&#x30A6;&#x30F3;&#x30C8;&#x306B;&#x5BFE;&#x3057;&#x3066;1&#x884C;](../.gitbook/assets/csv_account.png)

1. アカウント情報
2. AWSサービス毎の利用実績（USD）
3. 利用実績合計に対する消費税額（USD）
4. 利用実績合計（USD）

### CSVデータのフォーマット：アカウント/サービス単位

![1&#x30A2;&#x30AB;&#x30A6;&#x30F3;&#x30C8;&#x306E;1&#x30B5;&#x30FC;&#x30D3;&#x30B9;&#x3054;&#x3068;&#x306B;1&#x884C;](../.gitbook/assets/csv_service.png)

各アカウントのサービス毎に行を構成。

##  

