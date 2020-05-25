# MFA

The following endpoint is the base url for the APIs below.

```text
https://service.mobingi.com/m/mfa
```

## Create MFA

Create MFA setup for the user.

{% hint style="warning" %}
The MFA setup will only be fully enabled when the verify endpoint is successfully called
{% endhint %}

**Request**

```http
POST / HTTP1.1
authorization: Bearer {token}
content-type: application/json
```

**Response**

```ruby
HTTP/1.1 201 Created

{
  "user_id": "user",
  "user_type": "ripple-root",
  "secret": "secret",
  "url": "otpauth://totp",
  "recovery_codes": [
    "code"
  ],
  "status": "created",
  "created_at": "2020-05-25T06:10:07",
  "qr_code": "code"
}
```

## Verify MFA

Verify MFA setup for the user.

**Request**

```http
POST /verify HTTP1.1
authorization: Bearer {token}
content-type: application/json

{
  "passcode1": "123456",
  "passcode2": "123456"
}
```

**Response**

```ruby
HTTP/1.1 200 OK

{
  "success": true
}
```

## Get MFA status

Get MFA status for the user.

**Request**

```http
GET /status HTTP1.1
authorization: Bearer {token}
content-type: application/json
```

**Response**

```ruby
HTTP/1.1 200 OK

{
  "status": "created"
}
```

## Delete MFA

Disable MFA setup for the user.

**Request**

```http
DELETE / HTTP1.1
authorization: Bearer {token}
content-type: application/json
```

**Response**

```ruby
HTTP/1.1 200 OK

{
  "success": true
}
```
