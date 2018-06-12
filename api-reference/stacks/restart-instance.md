# インスタンスの再起動

```text
POST /v2/alm/stack/{stack_id}/restart_instance
```

| **Parameters** | **Type** | **Required** | **Details** |
| --- | --- |
| instance\_id | string | yes |  |

Request header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Request body:

```ruby
{
    "instance_id":"i-01164e4912759cbed"
}
```

Example response:

```ruby
HTTP/1.1 200 OK

{
    "status":"success",
    "reason":"Instance deleted from autoscaling group, with a protection of 3600 seconds."
}
```

