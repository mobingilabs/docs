# Update stack

```text
PUT /v2/alm/stack/{stack_id}
```

| **Parameters** | **Type** | **Required** | **Details** |
| --- | --- |
| configurations | json | no | This parameter is the same as [**Create Stack**](https://docs2.mobingi.com/v/v2/api-reference/stacks/update-stack)'s _configurations_ parameter. |

Request header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Request body:

```ruby
{
    "configurations":"{
        \"min\":1,
        \"max\":10
    }"
}
```

Example response:

```ruby
HTTP/1.1 200 OK
{
    "status":"UPDATE_IN_PROGRESS"
}
```

