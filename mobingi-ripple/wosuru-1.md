---
description: 新規顧客の追加方法です。
---

# 新規顧客を追加する

**手順**

* AWSで顧客のアカウントを追加
* 顧客（請求グループ）を登録する
* 顧客（請求グループ）データを登録する
* 請求グループにAWSアカウントを連結する
* Wave（Reseller閲覧用）ログイン情報を設定

## 1. 顧客（請求グループ）を登録する {#step1}

メニューより`請求グループ`を選択し、画面右上の`請求グループの追加`をクリック。

![&#x8ACB;&#x6C42;&#x30B0;&#x30EB;&#x30FC;&#x30D7;&#x30DA;&#x30FC;&#x30B8;](../.gitbook/assets/snip20180723_18.png)

下記フィールドを記入し`登録`する。

* 請求グループID：任意のIDを設定、もしくは `Generate!` ボタンで乱数を作成することができます。
* 請求グループ名：Rippleユーザー内で管理するためのグループ名です。**請求書の発行単位。**
* 企業名
* 電話番号
* 郵便番号
* 住所
* 宛名
* 支払いアカウント：Payer Account を選択します。 Payer Accountは`設定`で管理します。

## 2. 顧客（請求グループ）データを登録する {#step2}

**※ このデータ登録をしないと請求書の作成ができません。**

![](../.gitbook/assets/add_setting.png)



1. `設定`をクリック
2. 請求関連の諸条件を設定
   * 支払タイプ：日本円 / USドル
   * 割引率：パーセント
   * 消費税率：パーセント
   * AWSサポート請求方法
     * 一律パーセント
     * 開発者サポート
     * ビジネスサポート
     * エンタープライズサポート
   * 代行手数料請求方法

     * パーセント
     * 固定費
     * 自動（パーセント、固定費の大きい方）

     ※ 「請求書一括作成」を利用するには、これらを事前に設定する必要があります。

## 3. 請求グループにAWSアカウントを連結する {#step3}

![](../.gitbook/assets/add_account.png)



1. `アカウントの追加`をクリック。
2. 各フィールドを記入し`登録`する。
   * 請求グループ : 事前に作成されたものを選択。
   * アカウントID : 追加するAWSアカウントIDを記入。
   * アカウント名 : AWSアカウント名を記入。
   * 備考（任意）: 用途、目的などをメモ。

## 4. Wave（Reseller閲覧用）ログイン情報を設定 {#step4}

![](../.gitbook/assets/wave_setting.png)



1. `Wave`をクリック。
2. 各フィールドを記入し`登録`する。
   * 連結開始年月 ： Payer Accountへの連結を開始する年月（=今月）を選択。
   * ログインID/Eメール ： 任意のID（Emailなど）を設定。
   * ユーザー名 ： 任意の名前（貴社担当者、先方の担当者名など）を設定。

     ※ Waveログイン情報は請求グループごとにひとつ作成できます。
