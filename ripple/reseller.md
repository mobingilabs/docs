# Wave for Reseller

リセラーのAPIリファレンスは以下の通りです。

## Create reseller account

リセラーアカウントの発行

**Role actions**

* `ModifyReseller`

**Request**

```http
POST /reseller HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

{request body}
```

以下に`{request body}`のリクエストペイロードの例を示します。

**{request body}**

```ruby
{
  "email":"alphaus-cloud@alphaus.cloud",
  "company_id":"company1",
  "input_type":"Auto",
  "notification":true,
  "password":null
}
```

**request body description**

| Field | Type | Required | Validation | Description |
| :--- | :--- | :--- | :--- | :--- |
| email | _string_ | Yes | - | Eメールアドレス |
| company\_id | _string_ | Yes | - | 請求グループ内部ID |
| input\_type | _string_ | Yes | - Auto / Custom | Auto: パスワード自動生成 Custom: passwordを入力 |
| notification | _boolean_ | Yes | - | 作成時に通知をする/しない |
| password | _string_ | No | - | パスワード |
| meta | \[object\] | Yes | - | Wave機能表示設定。[metaについて](#meta) |

**Response**

```ruby
HTTP 200

{
  "status":"success"
}
```

## Get reseller account list

リセラーアカウントの取得

**Role actions**

* `ReadReseller`
* `ModifyReseller`

**Request**

```http
POST /reseller HTTP1.1
Authorization: Bearer {token}
```

**Response**

```ruby
HTTP 200

[
  {
    "user_id":"userid1",
    "billinggroup_id":"billing1",
    "billinggroup_name":"billingname1",
    "email":"alphaus-cloud@alphaus.cloud",
    "company_id":"company1",
    "update_time":null,
    "password_update_time":null,
    "wave_registered":"2020-01-01T10:00:00+09:00",
    "meta": {
      "dashboard_graph":true
      "usage_account":true
      "usage_account_graph":true
      "usage_account_menu_account_edit":false
      "usage_account_menu_budget":false
      "usage_account_menu_budget_edit":false
      "usage_account_menu_fees_fee":false
      "usage_account_menu_fees_credit":false
      "usage_account_menu_fees_refund":false
      "usage_report_download":true
      "usage_group":true
      "usage_group_graph":true
      "usage_tag":true
      "usage_tag_graph":true
      "usage_crosstag":true
      "usage_crosstag_graph":true
      "ri_purchased":true
      "ri_utilization":false
      "ri_recommendation":false
      "sp_purchased":false
      "invoice":false
      "invoice_download_csv_discount":false
      "invoice_download_csv_merged":false
      "open_api":false
      "users_management":false
    }
  },
  ...
]
```

## Delete reseller account

リセラーアカウントの削除

**Role actions**

* `ModifyReseller`

**Request**

```http
DELETE /reseller/{user_id} HTTP1.1
Authorization: Bearer {token}
```

**{user\_id}**

リセラーアカウントのidを指定する

**Response**

```ruby
HTTP 200

{
  "status":"success"
}
```

## Update password for reseller account

リセラーアカウントパスワードの変更

**Role actions**

* `ModifyReseller`

**Request**

```http
DELETE /reseller/{user_id}/password HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

{request body}
```

**{user\_id}**

リセラーアカウントのidを指定する

以下に`{request body}`のリクエストペイロードの例を示します。

**{request body}**

```ruby
{
  "input_type":"Auto",
  "notification":true,
  "password":null
}
```

**request body description**

| Field | Type | Required | Validation | Description |
| :--- | :--- | :--- | :--- | :--- |
| input\_type | _string_ | Yes | - Auto / Custom | Auto: パスワード自動生成 Custom: passwordを入力 |
| notification | _boolean_ | Yes | - | 変更時に通知をする/しない |
| password | _string_ | No | - | パスワード |

**Response**

```ruby
HTTP 200

{
  "status":"success"
}
```

### meta

metaのリストを示します。

`Default`はリセラーアカウントを発行する際に設定されるデフォルトの設定です。

| Field | Type | Default | Label(ja) | Description | 
| :---  | :--- | :---    | :---      | :---        |
| dashboard_graph | _boolean_ | true | ダッシュボード |ダッシュボードグラフの表示
| usage_account | _boolean_ | true | アカウントレポート | アカウント利用明細の表示 \[Account\] 
| usage_account_graph | _boolean_ | true | グラフの表示 \[アカウント\] | アカウント利用明細グラフの表示 \[Account\]
| usage_account_menu_account_edit | _boolean_ | false | アカウント名の編集 | アカウント名の編集 \[Account\]
| usage_account_menu_budget | _boolean_ | false | バジェットの表示 \[アカウント\] | バジェット設定の表示 \[Account\]
| usage_account_menu_budget_edit | _boolean_ | false | バジェットの編集 \[アカウント\] | バジェット設定の編集 \[Account\]
| usage_account_menu_fees_fee | _boolean_ | false | Feeの表示 [アカウント > その他明細情報]  | Feeの表示 \[Account\]
| usage_account_menu_fees_credit | _boolean_ | false | Creditの表示 [アカウント > その他明細情報] | Creditの表示 \[Account\]
| usage_account_menu_fees_refund | _boolean_ | false | Refundの表示 [アカウント > その他明細情報] | Refundの表示 \[Account\]
| usage_report_download | _boolean_ | true | レポートのダウンロード \[アカウント\] | 利用明細レポートのダウンロード表示 \[Account\]
| usage_group | _boolean_ | true | グループレポート | 利用明細の表示 \[Group\]
| usage_group_graph | _boolean_ | true | グラフの表示 \[グループ\] | 利用明細グラフの表示 \[Group\]
| usage_tag | _boolean_ | true | タグレポート | 利用明細の表示 \[Tag\]
| usage_tag_graph | _boolean_ | true | グラフの表示 \[タグ\] | 利用明細グラフの表示 \[Tag\]
| usage_crosstag | _boolean_ | true | クロスタグレポート | 利用明細の表示 [Cross Tag]
| usage_crosstag_graph | _boolean_ | true | グラフの表示 \[クロスタグ\] | 利用明細グラフの表示 [Cross Tag]
| ri_purchased | _boolean_ | true | 購入済みRIの表示 | 購入済みRIの表示
| ri_utilization | _boolean_ | false | RI適用率の表示 | RI適用率の表示
| ri_recommendation | _boolean_ | false | レコメンデーションの表示 | RIレコメンデーションの表示
| sp_purchased | _boolean_ | false | 購入済みSavingsPlansの表示 | 購入済みSavingsPlansの表示
| invoice | _boolean_ | false | 請求書の表示 | ご利用明細の表示
| invoice_download_csv_discount | _boolean_ | false | 割引詳細CSVのダウンロード | 割引詳細CSVのダウンロード \[Usage details\]
| invoice_download_csv_merged | _boolean_ | false | 請求書（統合版）CSVのダウンロード | 請求書（統合版）CSVのダウンロード \[Usage details\]
| open_api | _boolean_ | false | API アクセストークン | API アクセストークン \[Settings\]
| users_management | _boolean_ | false | サブユーザー管理 | サブユーザー管理 \[Settings\]