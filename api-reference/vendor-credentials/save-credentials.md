# Save credentials

```text
POST /v2/credentials/{vendor}
```

|  |  |  |  |
| --- | --- | --- |
| **Parameters** | **Type** | **Required** | **Details** |
| credentials | array | yes | contains credentials information \(see example request below\) |

Request header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Request body:

```ruby
{
  "credentials": {
    "AWSAccessKeyId": "*** your aws access key id ***",
    "AWSSecretKey": "*** your aws secret key ***",
    "AWSAccountName": "My Aws account 1"
  }
}
```

Response body:

```ruby
HTTP/1.1 200 OK

{
    "status":"success"
}
```

