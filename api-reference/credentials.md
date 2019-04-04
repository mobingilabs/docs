# Credentials

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

Before you can do any Ocean deployments, you need to register your cloud credentials to Ocean. These credentials will be used by Ocean to access your cloud account and deploy any resources you need in your Ocean deployments.

## Create a credential

```http
REQUEST
POST /v0/credentials HTTP1.1
Authorization: Bearer {token}

{request body contents vary per provider}

---
RESPONSE
HTTP 202
```

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

