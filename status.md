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
| `msp` | Required. The MSP id to query. |
| `vendor` | Optional. Supported vendor is only `aws`  at the moment. |
| `from` | Optional. If not provided, default value is 2 months before current month. Format: `yyyymm`. |
| `to` | Optional. If not provided, default value is current month. Format: `yyyymm`. |

Examples:

```bash
# Simple request. Get status for the past 2 months:
GET calculations/status?msp=MSP-123456

# If you want range from Oct 2019 - Jan 2020:
GET calculations/status?msp=MSP-123456&from=201910&to=202001
```
