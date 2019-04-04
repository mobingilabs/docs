# Credentials

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

Before you can do any Ocean deployments, you need to register your cloud credentials to Ocean. These credentials will be used by Ocean to access your cloud account and deploy any resources you need in your Ocean deployments.

## Create a credential

**Request**

```http
POST /v0/credentials HTTP1.1
Authorization: Bearer {token}

{request body}
```

The following are some example request payloads for `{request body}` per provider.

Alibaba:

```ruby
{
  "vendor":"alicloud",
  "name":"testalicloudcreds",
  "key":"ABCDEF",
  "secret":"somesecret"
}
```

AWS:

```ruby
{
  "vendor":"aws",
  "name":"testawscreds",
  "key":"ABCDEF",
  "secret":"somesecret"
}
```

Azure:

```ruby
{
  "vendor":"azure",
  "name":"testazurecreds",
  "key":"ABCDEF",
  "secret":"somesecret",
  "application":"997613dc-032a-440f-bead-2bb5b19ad002",
  "subscription":"c825c2bf-cdc5-4b96-9644-a1dd5144ae0f",
  "directory":"292cd594-02c7-4a56-86e7-e30615557e83"
}
```

GCP (for GCP, `secret` is your service account's JSON file):

```ruby
{
  "vendor":"gcp",
  "name":"testgcpcreds",
  "project_id":"gcp-project-id",
  "secret":"aGVsbG93b3JsZA==",
  "isbase64":true
}
```

**Response**

```ruby
HTTP 201

Example:
{
  "credential_id":"cred-aws-58c2297d25645-fa7vzi6E1l",
  "user_id":"1234567890",
  "username":"testsubuser",
  "name":"testawscreds",
  "key":"ABCDEF",
  "secret":"***",
  "create_time":"2019-04-04T04:16:02Z",
  "update_time":"2019-04-04T04:16:02Z",
  "vendor":"aws"
}
```

When creating [Ocean templates](https://docs.mobingi.com/v/ocean-en/reference-2018-07-02), you will use the credential's `name` part as the name for the template's credential entry. This name should be unique per account.

## List credentials

```http
REQUEST
GET /v0/credentials[?vendor={vendor-name}] HTTP1.1
Authorization: Bearer {token}

---
RESPONSE
HTTP 200
tbd
```

## Describe a credential

```http
REQUEST
GET /v0/credentials/{id} HTTP1.1
Authorization: Bearer {token}

---
RESPONSE
HTTP 200
tbd
```

## Delete a credential

```text
REQUEST
DELETE /v0/credentials/{id} HTTP1.1
Authorization: Bearer {token}

---
RESPONSE
HTTP 202
```

