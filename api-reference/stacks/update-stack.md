# スタックの更新

```text
PUT /v2/alm/stack/{stack_id}
```

| **Parameters** | **Type** | **Required** | **Details** |
| --- | --- |
| configurations | json | no | [スタックの作成](https://docs.mobingi.com/official/api/v2/jp#create-stack)の _configurations_ パラメーターと同じ |

Request header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Request body:

```ruby
{
    "configurations":"{
        \"min\":1,
        \"max\":10
    }"
}
```

Example response:

```ruby
HTTP/1.1 200 OK
{
    "status":"UPDATE_IN_PROGRESS"
}
```

