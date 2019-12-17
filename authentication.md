# Authentication

Before you can access Alphaus API services, you need to get an access token first. You will then use this token in your succeeding calls to the API using the `Authorization: Bearer {token}` HTTP header.

## Access token URL
| Product | Base URL |
| :--- | :--- |
| Ripple | `https://login.mobingi.com/ripple/access_token` |
| Wave | `https://login.mobingi.com/access_token` |

**Request**

```http
POST {baseurl}/access_token HTTP1.1
Content-Type: application/json

{body formdata}
```

**Response**

```ruby
HTTP 200
[
  {
    "namespace":"wave",
    "permissions":[
      "Admin",
      "ModifySettings",
      "..."
    ]
  },
  {
    "namespace":"ripple",
    "permissions":[
      "Admin"
    ]
  }
]
```
