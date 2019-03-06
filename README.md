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
      "ViewSettings",
      "ModifyAccountSettings",
      "ViewAccountSettings",
      "DownloadBulk",
      "DownloadReports",
      "ModifyGroups",
      "ViewGroups",
      "ModifyTags",
      "ViewTags"
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

