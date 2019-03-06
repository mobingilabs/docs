---
description: Mobingi Documentation
---

# Reference

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

| Description | Link |
| :--- | :--- |
| Base URL \(dev\) | `https://servicedev.mobingi.com/m/` |
| Base URL | `https://service.mobingi.com/m/` |

## List permissions

#### Wave Permissions

| Permission | Description |
| :--- | :--- |
| Admin | No restrictions. Root user, by default, has this permission. |
| ModifySettings | Allowed to modify global Wave settings. |
| ViewSettings | View global Wave settings only. |
| ModifyAccountSettings | Allowed to modify account level settings. |
| ViewAccountSettings | View account level settings only. |
| DownloadBulk | Allowed to download bulk CSV. |
| DownloadReports | Allowed to download reports CSV. |
| ModifyGroups | Allowed to modify groups. |
| ViewGroups | View groups only. |
| ModifyTags | Allowed to modify tags. |
| ViewTags | View tags only. |

REQUEST

```http
GET /rbac/permissions HTTP1.1
Authorization: Bearer {token}
```

RESPONSE

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

