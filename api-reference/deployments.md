# Deployments

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

## Create a deployment

**Request**

```http
POST /v0/deployments HTTP1.1
Authorization: Bearer {token}

{template body}
```

**Response**

```http
HTTP 202
```

Check out [https://github.com/mobingi/ocean-template-examples](https://github.com/mobingi/ocean-template-examples) for examples about `{template body}`. For details on how to write Ocean templates, check out this [reference](https://docs.mobingi.com/v/ocean-en/template-2018-07-02).

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

**Request**

```http
GET /v0/deployments/{id} HTTP1.1
Authorization: Bearer {token}
```

**Response**

```http
HTTP 200
```

## Delete a deployment

**Request**

```http
DELETE /v0/deployments/{templatename} HTTP1.1
Authorization: Bearer {token}
```
**Response**

```http
HTTP 202
```

