# スタック情報の取得

```text
GET /v2/alm/stack/{stack_id}
```

Request header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Example Response:

```ruby
[
  {
    "stack_id": "mo-5447826c880e8-v56QbKqA-tk",
    "auth_token": "AzPoBVghiCGAHz3cyPMRImBaQUJoF",
    "user_id": "5447826c880e8",
    "nickname": "Test Stack",
    "vendor": "AWS",
    "cred": "AKIAJ2*********2DZLA",
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
    "stack_status": "CREATE_COMPLETE",
    "instances": [
        {
            "InstanceId":"i-01164e4912759cbed",
            "ImageId":"ami-9f0c67f8",
            "InstanceType":"m3.medium",
            "PublicIpAddress":"54.250.172.11"
            ...
        }
    ]
    "dbinstances": [
        {
            "AllocatedStorage":"100",
            "AvailabilityZone":"ap-northeast-1a",
            "DBInstanceClass":"db.m3.large",
            ...
        }
    ]
  }
]
```

