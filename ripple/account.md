# Account

{% hint style="warning" %}
This is still a draft version.
{% endhint %}

アカウントのAPIリファレンスは以下の通りです。

## Create

アカウントの作成

**Role actions**

- `ModifyAccount`

**Request**

```http
POST /accts HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

{request body}
```

以下に`{request body}`のリクエストペイロードの例を示します。

**{request body}**

```ruby
{
	"vendor":"aws",
    "customer_id":"012345678912",
    "account_id":"919999618919"
	"company_id":"AJfdivbDjhvbpE",
	"name":"ripple customer1",
	"note":null
}
```

**{request body} description**

Field         | Type      | Required | Validation | Description
------------- | --------- | -------- | ---------- | -----------
customer_id   | *string*  | Yes      | - AWS 12桁 <br> - Azure 16~36桁 | - AWS AccountID <br> - Azure SubscriptionID
account_id    | *string*  | Yes      | - AWS 12桁 <br> - AZURE 7桁 | - AWS PayerAccountID <br> - Azure BillingID
company_id    | *string*  | Yes      | -          | 請求グループ内部ID
vendor        | *string*  | Yes      | - サポート: `aws`,`azure`  | 
name          | *string*  | Yes      | - 長さ: 3 ~ 100    | 登録する顧客名
note          | *string*  | No       | -          | 備考欄

**Response**

```ruby
HTTP 200

{"status":"success"}

HTTP 400 customer id が既に登録されている場合

{
  "code":"5005",
  "message":"account function exception",
  "description":"Customer id already exists."
}
```

## List

アカウントリストの取得

**Role actions**

- `ReadAccount` 
- `ModifyAccount`

**Request**

```http
GET /accts?vendor={vendor} HTTP1.1
Authorization: Bearer {token}

```

以下に`{vendor}`のパラメータの例を示します。

**{vendor}**

- aws
- azure

**Response**

```ruby
HTTP 200

[
  {
    "billinggroup_id":"Billing1",
    "billinggroup_name":"Billing1",
    "company_id":"AJfdivbDjhvbpE",
    "customer_id":"012345678912",
    "customer_name":"ripple customer1",
    "account_id":"919999618919",
    "vendor":"aws",
    "note":null,
    "payer":false,
    "service_discount":null,
    "project_id":null,
    "azure_customer_id":null
  },
  ...
]
```


## Update

アカウントの更新

**Role actions**

- `ModifyAccount`

**Request**

```http
PUT /accts/{customer_id}/edit HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

{request body}
```

以下に`{customer_id}`のパラメータの例を示します。

**{customer_id}**

AWS AccountID or Azure SubscriptionID


以下に`{request body}`のリクエストペイロードの例を示します。

**{request body}**


```ruby
{
	"vendor":"aws",
    "account_id":"919999618919"
	"company_id":"AJfdivbDjhvbpE",
	"name":"ripple customer1",
	"note":null
}
```

**{request body} description**

Field         | Type      | Required | Validation | Description
------------- | --------- | -------- | ---------- | -----------
account_id    | *string*  | Yes      | - AWS 12桁 <br> - AZURE 7桁 | - AWS PayerAccountID <br> - Azure BillingID
company_id    | *string*  | Yes      | -          | 請求グループ内部ID
vendor        | *string*  | Yes      | - サポート: `aws`,`azure`  | 
name          | *string*  | Yes      | - 長さ: 3 ~ 100    | 登録する顧客名
note          | *string*  | No       | -          | 備考欄

**Response**

```ruby
HTTP 200

{"status":"success"}

HTTP 400 customer id が登録されていない場合

{
  "code":"5005",
  "message":"account function exception",
  "description":"Customer id is not exists."
}
```

## Delete

アカウントの削除

**Role actions**

- `ModifyAccount`

**Request**

```http
DELETE /accts/{vendor}/{id} HTTP1.1
Authorization: Bearer {token}

```

以下に`{vendor}`のパラメータの例を示します。

**{vendor}**

- aws
- azure


以下に`{id}`フォーマットのパラメータの例を示します。

**{id}**

`{customer_id}|{account_id}`。 エンドポイント例: `/accts/aws/012345678912|919999618919`

**Response**

```ruby
HTTP 200

{"status":"success"}
```
