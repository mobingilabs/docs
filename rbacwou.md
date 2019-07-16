---
description: RBACページの利用方法を解説します。
---

# RBACを使う

## 1. ロールを作成する

画面右上の`ADD ROLE`ボタンをクリック。

ロールの名前を入力し、ロールに紐づく権限を指定し`CREATE ROLE`をクリックします。1つ1つの権限の内容は権限ページをご覧ください。

{% page-ref page="permissions.md" %}

よく利用されるロールの組み合わせをいくつかご紹介します。

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x3067;&#x304D;&#x308B;&#x3053;&#x3068;</th>
      <th style="text-align:left">&#x30B5;&#x30FC;&#x30D3;&#x30B9;</th>
      <th style="text-align:left">&#x6A29;&#x9650;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left">&#x5168;&#x3066;</td>
      <td style="text-align:left">Admin</td>
    </tr>
    <tr>
      <td style="text-align:left">&#x95B2;&#x89A7;&#x6A29;&#x9650;&#x306E;&#x307F;</td>
      <td style="text-align:left">WAVE</td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">&#x95B2;&#x89A7;&#x6A29;&#x9650;&#x306E;&#x307F;</td>
      <td style="text-align:left">RIPPLE</td>
      <td style="text-align:left">
        <p>ReadAccount, ReadBillingGroup, ReadInvoice,</p>
        <p>ReadInvoiceSettings, ReadReseller ReadRi, ReadSettings</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left">USER</td>
      <td style="text-align:left">ReadOnly</td>
    </tr>
    <tr>
      <td style="text-align:left"></td>
      <td style="text-align:left">ROLE</td>
      <td style="text-align:left">ReadOnly</td>
    </tr>
  </tbody>
</table>{% hint style="info" %}
各ロールの内容は後からでも編集可能ですが、ロールの内容を変更した場合はそのロールが付与されているサブユーザーにも影響します。
{% endhint %}

## 2. サブユーザーを作成する

`ADD USER`ボタンをクリックし、Login Informationの必要項目を埋めていきます。

Rolesでは先ほど作成したロールの一覧が表示されるため、作成するサブユーザーにアタッチしたいものにチェックを入れ`CREATE USER`をクリックします。

サブユーザーに付与したロールの種類を変更する場合は各ユーザー横の編集マークから付与しているロールを変更することが可能です。



