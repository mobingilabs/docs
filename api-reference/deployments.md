# Deployments

## Create a deployment

```http
REQUEST
POST /vendord/v0/deployments HTTP1.1
Authorization: Bearer {token}

{template body}

---
RESPONSE
HTTP 202
```

## List deployments

```http
REQUEST
GET /vendord/v0/deployments HTTP1.1
Authorization: Bearer {token}

---
RESPONSE
HTTP 200
tbd
```

## Describe a deployment

```http
REQUEST
GET /vendord/v0/deployments/{id} HTTP1.1
Authorization: Bearer {token}

---
RESPONSE
HTTP 200
tbd
```

## Delete a deployment

```text
REQUEST
DELETE /vendord/v0/deployments/{id} HTTP1.1
Authorization: Bearer {token}

---
RESPONSE
HTTP 202
```

