# Update ServerConfig

```text
PUT /v2/alm/serverconfig
```

| **Parameters** | **Type** | **Required** | **Details** |
| :--- | :--- | :--- | :--- |
| stack\_id | string | yes | ​ |
| filepath | string | no | Required if `privateKey` or `branch` are set |
| privateKey | string | no |  |
| branch | string | no |  |
| mackerelApiKey | string | no | Required if parameter key is set |
| envvars | array | no | Required if parameter key is set |
| keypair\_id | string | no | Required if parameter key is set |

Request header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Request body:

```ruby
{
    "stack_id":"mo-5447826c880e8-v56QbKqA-tk",
    "filepath":"git:\/\/github.com\/mobingilabs\/default-site-php"
}

or 

{
    "stack_id":"mo-5447826c880e8-v56QbKqA-tk",
    "mackerelApiKey" : "************",
}

or 
{
    "stack_id":"mo-5447826c880e8-v56QbKqA-tk",
    "envvars" : ["AWS_REGION": "ap-northeast-1", "TEST_USER_NAME": "testuser"],
}

or 
{
    "stack_id":"mo-5447826c880e8-v56QbKqA-tk",
    "keypair_id" : "421a3b5bc2",
}
```

Example response:

```ruby
HTTP/1.1 200 OK

{
    "status":"success"
}
```

