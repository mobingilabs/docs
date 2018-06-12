# スタック一覧の取得

```text
GET /v2/alm/stack
```

Request Header:

```text
Authorization: Bearer eyJ0eXAiOiJQiLCJhbGciOMeXzQfME
Content-Type: application/json
```

Response Body:

```ruby
HTTP/1.1 200 OK

[
  {
    "auth_token": "AzPoBVghiCGAHz3cyPMRImBaQUJoF",
    "user_id": "5447826c880e8",
    "nickname": "Test Stack",
    "configuration": {
      "image": "mobingi\/ubuntu-apache2-php5",
      "code": "git:\/\/github.com\/mobingilabs\/default-site-php",
      "max": "3",
      "type": "m3.medium",
      "min": "2",
      "region": "ap-northeast-1",
      "architecture": "art_elb",
      ...
    },
    "create_time": "2016-12-03T11:51:34+09:00",
    "stack_outputs": [
      {
        "OutputValue": "mo-5447826c880e8-ELB-B45HZIW6UW08-749188260.ap-northeast-1.elb.amazonaws.com",
        "OutputKey": "Address"
      },
      ...
    ],
    "stack_id": "mo-5447826c880e8-v56QbKqA-tk",
    "stack_status": "CREATE_COMPLETE"
  },
  ..
]
```

