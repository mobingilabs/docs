# User

{% hint style="warning" %}
This is still a draft version.
{% endhint %}

The following is the API reference for working with Ripple user.

## Get user

get user information for ripple.

**Role actions**

- `ModifySettings`

**Request**

```http
GET /user HTTP1.1
Authorization: Bearer {token}

```

**Response**

```ruby
HTTP 200

{
  "username": null,
  "msp_id": "abcdefg",
  "exchange_rate": [
    {
      "month": "2020-01",
      "rate": 107.01
    },
    {
      "month": "2020-02",
      "rate": 104
    },
    {
      "month": "2020-03",
      "rate": 109.45
    }
  ],
  "company_name": "Docs, Inc.",
  "email": "docs@alphaus.cloud",
  "language": "ja"
}
```