# レポート

**基本的なResponse Format**

```json
{
	vendor : [
		{
			id : string
			name : string
			date : [
				{
					blended_cost : number
                    date : string
                    timestamp : number
                    true_unblended_cost : number
                    unblended_cost : number
				},...
			]
		},...
	]
}
```

<br>

| Response value        | type     | description   |
| --------------------- | -------- | ------------- |
| `vendor`              | *array*  | パラメーターで指定したvendor 例 : `aws` |
| `id`                  | *string* |  - `service` servicename <br>  - `account` account id |
| `name`                | *string* |  - `service` servicename <br>  - `account` account name |
| `date`                | *array*  | 取得したデータ一覧 |
| `date`                | *string* | - `monthly` : `YYYY-MM` <br> - `daily` : `YYYY-MM-DD` |
| `timestamp`           | *number* | `date` のUNIXタイムスタンプ |
| `blended_cost`        | *number* | AWS CURの `lineitem/blendedcost`   |
| `unblended_cost`      | *number* | AWS CURの `lineitem/unblendedcost` |
| `true_unblended_cost` | *number* | mobingiで再計算したunblendedcost |

## レポートの取得

**Request**

```http
POST /v1/reports/{owner}/{resolution}?from={from}&to={to}&by={by}&vendor={vendor} HTTP1.1
Content-Type: application/json

```

`{Path Variables}` の例

| Path             |  description    |
| ---------------  | --------------  |
| `owner`          | 使用可能な値 - company |
| `resolution`     | 使用可能な値 - monthly / daily  | 


`{URL Params}` の例

```ruby
{
  "from":"2019-01-01",
  "to":"2019-02-01",
  "by":"service",
  "vendor":"aws"
}
```

| Params       |  description                |
| -----------  | --------------------------  |
| `from`       | 型 : *string* <br> フォーマット : *YYYY-MM_DD* <br> 説明 : <br> Monthly は自動的に `YYYY-MM`へ変換されます。 <br> Daily は自動的に `YYYY-MM-DD`へ変換されます。<br>   |
| `to`         | 型 : *string* <br> フォーマット : *YYYY-MM_DD* <br> 説明 : <br> Monthly は自動的に `YYYY-MM`へ変換されます。 <br> Daily は自動的に `YYYY-MM-DD`へ変換されます。<br>    | 
| `by`         | **使用可能な値** <br> 型 : *string* <br> - `service` | `account`  <br> |
| `vendor`     | **使用可能な値** <br> 型 : *string* <br> - `aws` |