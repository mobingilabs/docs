# Put lifecycle hook

{% code-tabs %}
{% code-tabs-item title="AWS only" %}
```text
PUT /v2/alm/stack/{stack_id}/lifecyclehook
```
{% endcode-tabs-item %}
{% endcode-tabs %}

| **Parameters** | **Type** | **Required** | **Details** |
| :--- | :--- | :--- | :--- |
| heartbeat | string | no | The time in seconds of which lifecyclehook will apply to instances \(in the same autoscaling group\) when terminates on scale-in or restarts. Default value is 3600. |

Request header:

```text
Authorization: Bearer eyJ0eXAiOiJ83fjQb3LzMeXzQfME
Content-Type: application/json
```

Request body:

```ruby
{
    "heartbeat":3600
}
```

Example response:

```ruby
HTTP/1.1 200 OK
{
    "status":"success"
}
```

