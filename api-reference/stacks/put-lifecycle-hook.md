# ライフサイクルフックの設定

{% code title="AWS only" %}
```text
PUT /v2/alm/stack/{stack_id}/lifecyclehook
```
{% endcode %}

| **Parameters** | **Type** | **Required** | **Details** |
| :--- | :--- | :--- | :--- |
| heartbeat | string | no | Auto Scaling グループ内のインスタンスがスケールイン、もしくは再起動する際に、一定時間待機状態にするライフサイクルフック機能の時間\(秒数\)の設定。デフォルト値は 3600 |

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

