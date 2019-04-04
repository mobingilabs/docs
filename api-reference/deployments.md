# Deployments

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

## Create a deployment

```http
REQUEST
POST /v0/deployments HTTP1.1
Authorization: Bearer {token}

{template body}

---
RESPONSE
HTTP 202
```

Check out [https://github.com/mobingi/ocean-template-examples](https://github.com/mobingi/ocean-template-examples) for examples about `{template body}`.

## List deployments

```http
REQUEST
GET /v0/deployments HTTP1.1
Authorization: Bearer {token}

---
RESPONSE
HTTP 200
tbd
```

## Describe a deployment

```http
REQUEST
GET /v0/deployments/{id} HTTP1.1
Authorization: Bearer {token}

---
RESPONSE
HTTP 200
tbd
```

## Delete a deployment

```text
REQUEST
DELETE /v0/deployments/{id} HTTP1.1
Authorization: Bearer {token}

---
RESPONSE
HTTP 202
```

