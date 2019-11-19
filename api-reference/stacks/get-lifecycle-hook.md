# ライフサイクルフックの取得

{% code title="AWS only" %}
```text
GET /v2/alm/stack/{stack_id}/lifecyclehook
```
{% endcode %}

Request header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Example response:

```ruby
HTTP/1.1 200 OK

{
    "LifecycleTransition": "autoscaling:EC2_INSTANCE_TERMINATING",
    "GlobalTimeout": "172800",
    "LifecycleHookName": "mo-5447826c880e8-BHqH3h6XN-tk-lch-ists-tmnt",
    "HeartbeatTimeout": "3600"
}
```

