# Reseller

リセラーのAPIリファレンスは以下の通りです。

## Create reseller account

リセラーアカウントの発行


**Role actions**

- `ModifyReseller`

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

Field           | Type      | Required | Validation | Description
--------------- | --------- | -------- | ---------- | -----------
 email          | *string*  | Yes      | -          | Eメールアドレス
 company_id     | *string*  | Yes      | -          | 請求グループ内部ID
 input_type     | *string*  | Yes      | - Auto / Custom | Auto: パスワード自動生成 Custom: passwordを入力
 notification   | *boolean* | Yes      | -          | 作成時に通知をする/しない
 password       | *string*  | No       | -          | パスワード

**Response**

```ruby
HTTP 200

{
  "status": "success"
}
```


## Get reseller account list

リセラーアカウントの取得


**Role actions**

- `ReadReseller`
- `ModifyReseller`

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
      "dashboard_graph":true,
      "usage_account":true,
      "usage_account_graph":true,
      "usage_account_menu_account_edit":false,
      "usage_account_menu_budget":false,
      "usage_account_menu_budget_edit":false,
      "usage_account_menu_fees_fee":false,
      "usage_account_menu_fees_credit":false,
      "usage_account_menu_fees_refund":false,
      "usage_report_download":true,
      "usage_group":true,
      "usage_group_graph":true,
      "usage_tag":true,
      "usage_tag_graph":true,
      "usage_crosstag":true,
      "usage_crosstag_graph":true,
      "ri_purchased":true,
      "ri_utilization":false,
      "ri_recommendation":false,
      "sp_purchased":false,
      "invoice":false,
      "open_api":false,
      "users_management":true
    }
  },
  ...
]
```


## Delete reseller account

リセラーアカウントの削除


**Role actions**

- `ModifyReseller`

**Request**

```http
DELETE /reseller/{user_id} HTTP1.1
Authorization: Bearer {token}

```

**{user_id}**

リセラーアカウントのidを指定する

**Response**

```ruby
HTTP 200

{
  "status": "success"
}
```

## Update password for reseller account

リセラーアカウントパスワードの変更


**Role actions**

- `ModifyReseller`

**Request**

```http
DELETE /reseller/{user_id}/password HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

{request body}
```

**{user_id}**

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

Field           | Type      | Required | Validation | Description
--------------- | --------- | -------- | ---------- | -----------
 input_type     | *string*  | Yes      | - Auto / Custom | Auto: パスワード自動生成 Custom: passwordを入力
 notification   | *boolean* | Yes      | -          | 作成時に通知をする/しない
 password       | *string*  | No       | -          | パスワード

**Response**

```ruby
HTTP 200

{
  "status": "success"
}
```