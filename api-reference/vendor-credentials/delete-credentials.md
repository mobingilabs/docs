# Delete credentials

```text
DELETE /v2/credentials/{vendor}
```

| **Parameters** | **Type** | **Required** | **Details** |
| :--- | :--- | :--- | :--- |
| credential\_id | string | yes |  |

Request header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Request body:

```ruby
{
    "credential_id":"*** your aws access key id **"
}
```

Example response:

```ruby
HTTP/1.1 200 OK

{
    "status":"success"
}
```

