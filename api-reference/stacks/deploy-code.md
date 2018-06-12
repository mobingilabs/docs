# Deploy code

```text
POST /v2/alm/stack/{stack_id}/code
```

| **Parameters** | **Type** | **Required** | **Details** |
| --- | --- | --- | --- |
| method | string | yes | Options are `s3`, `github_public`,`github_private`, or `github` |
| filepath | string | no | When 'method' is `s3` or `github_public` or `github_private`, this value is required |
| privateKey | string | no | When 'method' is `github_private`, this value is required |

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

