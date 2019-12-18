# Authentication

Before you can access Alphaus API services, you need to get an access token first. You will then use this token in your succeeding calls to the API using the `authorization: Bearer {token}` HTTP header. Alphaus API tokens are [JSON Web Tokens \(JWT\)](https://tools.ietf.org/html/rfc7519).

Use the following endpoints to acquire product-specific access tokens. Tokens are not compatible between the two. Ripple access tokens can only be used for Ripple endpoints; Wave access tokens are only valid on Wave endpoints.

```bash
# Ripple
https://login.mobingi.com/ripple/access_token

# Wave
https://login.mobingi.com/access_token
```

**Request**

To obtain an access token, send a POST message to the access token endpoint using the format described below.

```http
POST {access-token-url} HTTP1.1
content-type: multipart/form-data

{body formdata}
```

The following table describes the formdata you need to supply as your POST body.

| Name | Value |
| :--- | :--- |
| `grant_type` | Valid values: `password`, 'client_credentials' |
| `client_id` | The client id you received from Alphaus. |
| `client_secret` | The client secret you received from Alphaus. |
| `username` | You account username. Required if `grant_type` is set to `password`. |
| `password` | You account password. Required if `grant_type` is set to `password`. |
| `scope` | Valid values: `openid` |

**Response**

```ruby
HTTP/1.1 200 OK

{
  "id_token": "eyJ0eXAiOiJKV1Q...",
  "token_type": "Bearer",
  "expires_in": 86400,
  "access_token": "eyJ0eXAiOiJKV1Q...",
  "refresh_token": "def50200..."
}
```

