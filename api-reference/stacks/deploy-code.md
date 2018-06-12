# コードの実行

```text
POST /v2/alm/stack/{stack_id}/code
```

| **Parameters** | **Type** | **Required** | **Details** |
| --- | --- | --- | --- |
| method | string | yes | オプションは `s3`,`github_public` 、`github_private` 、`github` 。 |
| filepath | string | no | 「method」が `s3` 、 `github_public` 、 `github_private` のいずれかの場合、この値は必須です。 |
| privateKey | string | no | 「method」が `github_private` の場合、この値は必須です。 |

Request header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Request body:

```ruby
{
    "method":"github_public",
    "filepath":"git://github.com/mobingilabs/default-site-php"
}
```

Example response:

```ruby
HTTP/1.1 200 OK
{
    "status":"success"
}
```

