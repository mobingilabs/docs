# ServerConfigの取得

```text
GET /v2/alm/serverconfig?stack_id={stack_id}
```

| **Parameters** | **Type** | **Required** | **Details** |
| --- | --- |
| stack\_id | string | yes |  |

Request header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Example response:

```ruby
HTTP/1.1 200 OK

{
    "image":"mobingi\/ubuntu-apache2-php5",
    "code":"git:\/\/github.com\/mobingilabs\/default-site-php",
    "codeDir":"\/srv\/code\/",
    "ports":[
        80,
        443
    ],
    "environmentVariables":[],
    "updated":1479374854,
    "version":"2017-02-01",
}
```

