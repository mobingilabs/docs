# ExchangeRate

{% hint style="warning" %}
This is still a draft version.
{% endhint %}

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

月ごとの為替レートの取得。ドキュメント[`get:/user`](WIP) レスポンス`{exchange_rate}`から確認できます。

