# Status

{% hint style="warning" %}
This is still a draft version.
{% endhint %}

The following endpoint is the base url for the APIs below.

```text
https://service.mobingi.com/m/status/
```

## List invoice calculation status

Get the current status of the invoice calculations.

**Request**

```http
GET calculations/status[?params] HTTP1.1
Authorization: Bearer {token}
```

Details for `params`.

| Key | Value |
| :--- | :--- |
| `vendor` | Optional. Supported vendor is only aws  at the moment. |
| `from` | Optional. If not provided, default value is 2 months before current month. |
| `to` | Optional. If not provided, default value is current month. |
