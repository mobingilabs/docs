# Authorization \(RBAC\)

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

Roles are root user-level. That means all roles created by the root user, or any subuser that has permissions to create roles, are available to all subusers.

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

**Response**

```ruby
HTTP 200
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

The `{namespace}` parameter is optional. If not provided, all roles will be returned.

**Response**

```ruby
HTTP 200
[
  {
    "name": "testrole",
    "namespace": "wave",
    "permissions": [
      "ModifySettings",
      "ViewSettings",
      "ModifyAccountSettings"
    ]
  },
  {
    "name": "waveAdmin",
    "namespace": "wave",
    "permissions": [
      "Admin"
    ]
  },
  ...
]
```

## Update role

Update role.
if role name is different, rename mapped role name.

**Request**

```http
PATCH /roles/{role-name} HTTP1.1
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

## Delete role

Delete role and delete mapped role.

**Request**

```http
DELETE /roles/{role-name} HTTP1.1
Authorization: Bearer {token}
```

## Map roles to user

You can only map \(or attach\) up to 5 roles to a user per namespace. There is no limit for filtering rules per user.

Valid values for `type` for filtering rules:

| Namespace | Value |
| :--- | :--- |
| `wave` | `linkAcct`, `group`, `tags` |
| `ripple` | `billingGroup` |

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
    "somerole",
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

For this endpoint, the returned role mappings are those attached to the caller.

```http
GET /userroles HTTP1.1
Authorization: Bearer {token}
```

For listing role mappings of other subusers, use this endpoint.

```http
GET /{subuser}/userroles HTTP1.1
Authorization: Bearer {token}
```

`{subuser}` is the subuser name.

**Response**

```ruby
HTTP 200
[
  {
    "root_user":"58c2297d25645",
    "sub_user":"subuser01",
    "namespace":"wave",
    "role":"testrole1"
  },
  {
    "root_user":"58c2297d25645",
    "sub_user":"subuser02",
    "namespace":"wave",
    "filter":"billingGroup:2222"
  },
  ...
]
```

## Update map roles to user

You can only update map \(or attach\) up to 5 roles to a user per namespace. There is no limit for filtering rules per user.

Valid values for `type` for filtering rules:

| Namespace | Value |
| :--- | :--- |
| `wave` | `linkAcct`, `group`, `tags` |
| `ripple` | `billingGroup` |

This method replaces subuser's all roles to information in the request body.

**Request**

```http
PATCH /userroles HTTP1.1
Authorization: Bearer {token}
```

```http
PATCH /{subuser}/userroles HTTP1.1
Authorization: Bearer {token}
```

`{subuser}` is the subuser id.

**Request body**

```ruby
{
  "namespace":"wave",
  "roles":[
    "somerole",
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

## Delete user role mapping

delete user role map.
don't delete filter.

**Request**

```http
DELETE /userroles/{role-name} HTTP1.1
Authorization: Bearer {token}
```

```http
DELETE /{subuser}/userroles/{role-name} HTTP1.1
Authorization: Bearer {token}
```

`{subuser}` is the subuser name.


**Response**

```ruby
HTTP 200
```