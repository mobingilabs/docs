# Users

The following APIs are used to manage your account's subusers.

| Description | Link |
| :--- | :--- |
| API Base URL | `https://service.mobingi.com/m/u/` |

## Create subuser

Create new subuser.

**Request**

```http
POST /users HTTP1.1
authorization: Bearer {token}
content-type: application/json

{body}
```

Details for the POST `{body}`.

| Key | Value |
| :--- | :--- |
| `username` | Required. Min: 4, max: 18, allowed characters: letters, numbers, _ (underscore), . (period) and - (hyphen) |

**Response**

```ruby
HTTP/1.1 200 OK

[
  {
    "username":"mysubuser",
    "msp_user":"MSP-123456",
    "mobingi_user": "abcdef",
    "email":"mysubuser@domain.com",
    "nickname":"",
    ...
  }
]
```

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
    "mobingi_user": "abcdef",
    "email":"mysubuser@domain.com",
    "nickname":"",
    ...
  }
]
```

