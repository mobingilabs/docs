# ExchangeRate

The following is the API reference for working with Ripple exchange rate.

## Set exchange rate per month

Set exchange rate per month.


**Role actions**

- `ModifySettings`

**Request**

```http
POST /user/exchange HTTP1.1
Authorization: Bearer {token}
Content-Type: application/json

{request body}
```
The following are some example request payloads for `{request body}`.


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

Field             | Type      | Required | Validation | Description
----------------- | --------- | -------- | ---------- | -----------
 `rate`           | *double*  | Yes      | -          | Exchange rate
 `month`          | *string*  | Yes      | -          | Target month


**Response**

```ruby
HTTP 200

{
  "status": "success"
}
```


## List exchange rate

Get a list of exchange rate per month. you can check [`get:/user`](WIP) document.

