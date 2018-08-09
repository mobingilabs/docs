---
description: Mobingi Waveにログインする
---

# Mobingi Wave 概要

## Mobingi Waveにログインする

![](../.gitbook/assets/wave01.png)

* https://app.mobingi.com/wave/login より必要情報を入力し、ログインをクリック。

## メニュー構成

![](../.gitbook/assets/snip20180720_21.png)

* ダッシュボード：貴社でご利用の全てのAWSアカウントの利用状況（合計）可視化。
* レポート：アカウント単位、グループ単位、タグ単位の利用状況を可視化、レポートの参照。
* RI：Reserved Instanceの一覧と適応状況を表示。

## ダッシュボード

![](../.gitbook/assets/snip20180809_2.png)

* 日次更新データについて
  * 更新タイミング：毎日
  * データ鮮度：約2日前のデータ
* 月次更新データについて
  * 更新タイミング：毎月5日頃
  * データ鮮度：先月以前の利用分を表示

## ダッシュボード -Analysis

![](../.gitbook/assets/snip20180809_3.png)

* Daily
  * 合計：今月の利用料の累積（Usage hr x on-demand rate）
  * 日別データの平均額：今月の日次利用料の変動（Usage hr x on-demand rate）
* Monthly
  * 過去12ヶ月間の利用料の推移（Usage hr x true rate） アカウント毎に色分け

## レポート -アカウント

選択するアカウントごとの利用実績を確認できます。

![](../.gitbook/assets/snip20180720_23.png)

* Payer : Payer account \(親アカウント）
* ![](../.gitbook/assets/screen-shot-2018-06-11-at-13.58.08.png):予算（アラート通知）設定されている。

スクロールし、年月、サービスを選択するとレポートが表示できます。  
年月の隣にあるボタンからCSVとしてダウンロードできます。

![](../.gitbook/assets/snip20180720_24.png)

## レポート - グループ

複数のアカウントをグルーピングし、グループごとの利用金額を表示します。 

![](../.gitbook/assets/snip20180720_26.png)

## レポート - タグ

AWSで利用しているタグごとの利用金額を把握できます。

![](../.gitbook/assets/snip20180724_32.png)

詳細は[タグでの利用量](https://docs.mobingi.com/v/wave/mobingi-wave/tag-report)の把握をご覧ください。

## RI - Reserved Instance

購入済みのRIを確認できます。

![](../.gitbook/assets/wave_ri.png)

## 請求書

月々の請求書を確認することができます。

![](../.gitbook/assets/wave_invoice.png)

## 設定

以下の設定、変更が可能です。

* パスワードの変更
* 言語の変更（日本語・英語・中国語）
* 通知設定（メール・Slack）

