# Reference

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

| Description | Link |
| :--- | :--- |
| Base URL | `https://service.mobingi.com/m/auth/rbac/` |

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
    "namespace":"global",
    "permissions":[
      "Admin"
    ]
  },
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
GET /roles HTTP1.1
Authorization: Bearer {token}
```

**Response**

```ruby
HTTP 200
[
  {
    "id": "6f6e6561646d696e...",
    "roles": {
      "name": "adminrole",
      "permissions": [
        {
          "namespace": "wave",
          "permissions": [
            "Admin"
          ]
        }
      ]
    }
  },
  {
    "id": "6f726564726f6c65...",
    "roles": {
      "name": "testrole",
      "permissions": [
        {
          "namespace": "wave",
          "permissions": [
            "ModifySettings",
            "ViewSettings",
            "ModifyAccountSettings"
          ]
        }
      ]
    }
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

## Attach roles to user

You can only attach up to 10 roles per user. Attaching roles to users always overwrite existing mapped roles at namespace level. For example, if a user has 3 roles attached to it, namely `role1`, `role2`, and `role3`, if you attach `role4` to that same user, that user will now only have one role, namely `role4`. Passing an empty roles list will not remove any mapping.

**Request**

```http
POST /userroles HTTP1.1
Authorization: Bearer {token}
```

**Request body**

```ruby
{
  "user_id":"subuser1",
  "roles":[
    "MjI5N2QyNTY0NVw6...",
    "Mm5kYWRtaW4gNThj...",
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
  "failed":[]
}
```

## List user roles

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
    "root_user":
    "58c2297d25645",
    "sub_user":"subuser02",
    "namespace":"wave",
    "role":"testrole2"
  }
]
```
