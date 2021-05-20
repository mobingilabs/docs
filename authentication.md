# Authentication

{% hint style="info" %}
Authentication for [Wave \(OpenAPI\)](https://docs.mobingi.com/v/api-reference/wave-open-api/prerequest) is separated at the moment. We will be unifying all logins for all our APIs going forward. An announcement will be made once it's done.
{% endhint %}

Before you can access Alphaus API services, you need to get an access token first. You will then use this token in your succeeding calls to the API using the `Authorization: Bearer {token}` HTTP header. Alphaus API tokens are [JSON Web Tokens \(JWT\)](https://tools.ietf.org/html/rfc7519).

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
Content-Type: multipart/form-data

{body formdata}
```

The following table describes the formdata you need to supply as your POST body.

| Name | Value |
| :--- | :--- |
| `grant_type` | Valid values: `password`, `client_credentials` |
| `client_id` | The client id you received from Alphaus or from API. |
| `client_secret` | The client secret you received from Alphaus or from API. |
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

**Using bluectl**

You can also use our [bluectl](https://github.com/alphauslabs/bluectl) CLI tool to generate access tokens. It is designed to work with the `client_credentials` grant type, although it supports the `password` grant type as well.

```bash
# Uses environment variables:
# For Ripple:
#   ALPHAUS_RIPPLE_CLIENT_ID
#   ALPHAUS_RIPPLE_CLIENT_SECRET
$ bluectl ripple access-token

# For Wave:
#   ALPHAUS_WAVE_CLIENT_ID
#   ALPHAUS_WAVE_CLIENT_SECRET
$ bluectl wave access-token

# You can also provide the credentials directly if you prefer:
$ bluectl ripple access-token --client-id=id --client-secret=secret

# You can also access our beta (next) environment:
$ bluectl ripple access-token --beta

# Use with other commands (example):
$ curl -H "Authorization: Bearer $(bluectl ripple access-token)" \
  https://some-ripple-endpoint/...
```

