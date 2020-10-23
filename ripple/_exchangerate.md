# ExchangeRate


為替レートのAPIリファレンスは以下の通りです。

## Set exchange rate per month

月ごとの為替レートの更新


**Role actions**

- `ModifySettings`

**Request**

```http
POST /user/exchange HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

{request body}
```

以下に`{request body}`のリクエストペイロードの例を示します。

**{request body}**

```ruby
{
	"exchange_rate":
		{
			"rate":110,
			"month":"2020-01"
		}
}
```

**exchange_rate object description**

Field           | Type      | Required | Validation | Description
--------------- | --------- | -------- | ---------- | -----------
 rate           | *double*  | Yes      | -          | 為替レート
 month          | *string*  | Yes      | -          | 対象月


**Response**

```ruby
HTTP 200

{
  "status": "success"
}
```


## List exchange rate

月ごとの為替レートの取得。ドキュメント[`get:/user`](https://docs.mobingi.com/v/api-reference/ripple/user) レスポンス`{exchange_rate}`から確認できます。


## Set invoice exchange rate per month

月ごとの請求書設定の為替レートの更新


**Role actions**

- `ModifyInvoice`

**Request**

```http
POST /invoices/exchangerate/{month} HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

{request body}
```

リクエストパラーメータの`{month}`のフォーマット: `yyyy-mm` 例: 2020-01

以下に`{request body}`のリクエストペイロードの例を示します。

**{request body}**

```ruby
{
  "vendor": "aws",
  "billing_groups": [
    "abcdfeg",
    "hijklmn"
  ],
  "exchange_rate": 105.076
}
```

Field           | Type      | Required | Validation | Description
--------------- | --------- | -------- | ---------- | -----------
 vendor         | *string*  | Yes      | サポート: `aws`, `azure` | ベンダー
 billing_groups | *object*  | Yes      | -          | 請求グループ一覧
 exchange_rate  | *double*  | Yes      | -          | 為替レート


**Response**

```ruby
HTTP 200

{
  "status": "success"
}
```