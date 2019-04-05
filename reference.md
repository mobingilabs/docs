# API Reference

| Description | Link |
| :--- | :--- |
| API Base URL | `https://service.mobingi.com/m/auth/rbac/` |

## List permissions

**Request**

```http
GET /permissions HTTP1.1
Authorization: Bearer {token}
```

**Response**

```ruby
HTTP 200
[
  {
    "namespace":"wave",
    "permissions":[
      "Admin",
      "ModifySettings",
      "..."
    ]
  },
  {
    "namespace":"ripple",
    "permissions":[
      "Admin"
    ]
  }
]
```

## Create role

During role creation, if your `permissions` list contains an `Admin` entry, all other entries will be discarded except `Admin`.

**Request**

```http
POST /roles HTTP1.1
Authorization: Bearer {token}
```

**Request body**

```ruby
{
  "name":"testrole",
  "permissions":[
    {
      "namespace":"wave",
      "permissions":[
        "ModifySettings",
        "ViewSettings",
        ...
      ]
    }
  ]
}
```

## List roles

**Request**

```http
GET /roles?namespace={namespace} HTTP1.1
Authorization: Bearer {token}
```

**Response**

```ruby
HTTP 200
[
  {
    "id": "b3JlZHJvbGUgNThjMjI5N2Q...",
    "name": "testrole",
    "namespace": "wave",
    "permissions": [
      "ModifySettings",
      "ViewSettings",
      "ModifyAccountSettings"
    ]
  },
  {
    "id": "Mm5kYWRtaW4g...",
    "name": "waveAdmin",
    "namespace": "wave",
    "permissions": [
      "Admin"
    ]
  },
  ...
]
```

## Delete role

**Request**

```http
DELETE /roles/{id} HTTP1.1
Authorization: Bearer {token}
```

The `{id}` part is the value of the `id` you get from listing roles.

## Map roles to user

You can only map \(or attach\) up to 5 roles per user per namespace. There is no limit for filtering rules per user.

Valid values for `type` for filtering rules:

| Namespace | Value |
| :--- | :--- |
| wave | `linkAcct` |
|  | `group` |
|  | `tags` |
| ripple | `billingGroup` |

**Request**

```http
POST /userroles HTTP1.1
Authorization: Bearer {token}
```

**Request body**

```ruby
{
  "user_id":"subuser1",
  "namespace":"wave",
  "roles":[
    "MjI5N2QyNTY0NVw6...",
    "Mm5kYWRtaW4gNThj...",
    ...
  ],
  "filter_rules":[
    {
      "type":"linkAcct",
      "resource":[
        "1111",
        "2222",
        ...
      ]
    },
    {
      "type":"billingGroup",
      "resource":[
        "3333",
        "4444",
        ...
      ]
    },
    ...
  ]
}
```

**Response**

```ruby
HTTP 200
{
  "success":[
    "somerole"
  ],
  "failed":[],
  "filters":[]
}
```

## List user role mappings

**Request**

```http
GET /userroles HTTP1.1
Authorization: Bearer {token}
```

**Response**

```ruby
HTTP 200
[
  {
    "id":"NThjMjI5N2QyN...",
    "root_user":"58c2297d25645",
    "sub_user":"subuser01",
    "namespace":"wave",
    "role":"testrole1"
  },
  {
    "id":"NThjMjI5N2QyNTY0NXx...",
    "root_user":"58c2297d25645",
    "sub_user":"subuser02",
    "namespace":"wave",
    "filter":"billingGroup:2222"
  },
  ...
]
```

## Delete user role mapping

**Request**

```http
DELETE /userroles/{id} HTTP1.1
Authorization: Bearer {token}
```

The `{id}` part is the value of the `id` you get from listing user role mappings.

