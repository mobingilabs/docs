# プリリクエスト

open apiを使用するためのtokenを取得する必要があります。

**Response Format**
```
{
    token_type : string
    expires_in : number
    access_token : string
}
```

<br>

| Response value  | type      | description   |
| --------------- | --------- | ------------- |
| `token_type`    | *string*  | 認証スキーム |
| `expires_in`    | *number*  | 期限 43200秒 |
| `access_token`  | *string*  | token値 |

## Token取得

openapiで使用するtokenを取得

**Request**

```http
POST /v1/access_token HTTP1.1
Content-Type: form-data

{request body}
```

`{request body}` の例

```ruby
{
  "grant_type":"client_credentials",
  "client_id":"test-client-id",
  "client_secret":"ABCDEFGHI"
}
```

| Body             |  description    |
| ---------------  | --------------  |
| `grant_type`     | 固定値           |
| `client_id`      | 顧客ID           | 
| `client_secret`  | 顧客Secret       |