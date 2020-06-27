# API clients

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

The following endpoint is the base url for the APIs below.

```text
https://service.mobingi.com/m/u/users/
```

## Create API client

Create a new API client under a specific user.

**Request**

```http
POST /client/:user HTTP1.1
authorization: Bearer {token}
content-type: application/json

{
  "name": "test-apiclient-name",
}
```

`:user` is either root user or subuser.

Details for the POST `{body}`.

| Key | Value |
| :--- | :--- |
| `name` | Required. The name of the API client. |

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

## List API clients

List all API clients under a specific user.
