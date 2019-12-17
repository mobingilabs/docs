# Users

The following APIs are used to manage your account's subusers.

| Description | Link |
| :--- | :--- |
| API Base URL | `https://service.mobingi.com/m/u/` |

## Create subuser

TBD

## List subusers

List all subusers.

**Request**

```http
GET /users HTTP1.1
authorization: Bearer {token}
```

**Response**

```ruby
HTTP/1.1 200 OK

[
  {
    "username":"mysubuser",
    "msp_user":"MSP-123456",
    "email":"mysubuser@domain.com",
    "nickname":"",
    "notification": {
      "email":"false"}
    },
    ...
  }
]
```

