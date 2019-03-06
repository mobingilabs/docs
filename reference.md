# Reference

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

| Description | Link |
| :--- | :--- |
| Base URL | `https://service.mobingi.com/m/` |

## List permissions

#### Request

```http
GET /rbac/permissions HTTP1.1
Authorization: Bearer {token}
```

#### Response

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

During role creation, if your `permissions` list contains an `Admin` entry, all other entries will be discarded.

#### Request

```http
POST /rbac/roles HTTP1.1
Authorization: Bearer {token}
```

#### Request body

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

#### Request

```http
GET /rbac/roles HTTP1.1
Authorization: Bearer {token}
```

#### Response

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

#### Request

```http
DELETE /rbac/roles/{id} HTTP1.1
Authorization: Bearer {token}
```

The `{id}` part is the value of the `id` you get from listing roles.

