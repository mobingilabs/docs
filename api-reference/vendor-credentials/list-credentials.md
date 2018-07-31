# List credentials

```text
GET /v2/credentials/{vendor}
```

Request header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Response body:

```ruby
HTTP/1.1 200 OK

[
    {
        "id": "*** your aws access key id ***",
        "account": "My Aws account 1",
        "lastModified": "2017-01-21T06:39:06.000Z"
    },
    {
        "id": "*** your aws access key id ***",
        "account": "My Aws account 2",
        "lastModified": "2017-01-21T06:33:10.000Z"
    },
    ...
]
```

