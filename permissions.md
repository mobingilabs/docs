# Permissions

The following tables list all supported permissions under Mobingi RBAC across all namespaces.

## Dashboard permissions

The following table lists the permissions supported under Mobingi Dashboard. Dashboard permissions belong to the `dashboard` namespace.

| Permission | Description |
| :--- | :--- |
| `Admin` | No restrictions. Root user, by default, has this permission. |
| `ReadEventsAll` | View events under all namespaces. |
| `ReadEventsRipple` | View events under `ripple` namespace. |
| `ReadEventsWave` | View events under `wave` namespace. |
| `ReadEventsOcean` | View events under `ocean` namespace. |

## RBAC permissions

The following table lists the permissions supported under RBAC management. RBAC permissions belong to the `rbac` namespace.

| Permission | Description |
| :--- | :--- |
| `Admin` | No restrictions. Root user, by default, has this permission. |
| `ReadOnly` | View RBAC permissions, roles, and mappings. |
| `ModifyRoles` | Allowed to modify RBAC roles. |
| `ModifyUserRoles` | Allowed to modify user-role mappings. |

## Wave permissions

The following table lists the permissions supported under RBAC for Wave. Wave permissions belong to the `wave` namespace.

| Permission | Description |
| :--- | :--- |
| `Admin` | No restrictions. Root user, by default, has this permission. |
| `ModifySettings` | Allowed to modify global Wave settings. |
| `ReadSettings` | View global Wave settings only. |
| `ModifyAccountSettings` | Allowed to modify account level settings. |
| `ReadAccountSettings` | View account level settings only. |
| `ReadAccount` | View account list only. |
| `DownloadBulk` | Allowed to download bulk CSV. |
| `DownloadReports` | Allowed to download reports CSV. |
| `ModifyGroups` | Allowed to modify groups. |
| `ReadGroups` | View groups only. |
| `ModifyTags` | Allowed to modify tags. |
| `ReadTags` | View tags only. |
| `ReadBillingGroup` | View billing group dashboard data \(graph\) only. |
| `ModifyBillingGroup` | Allowed to modify billing group dashboard data. |

## Ripple permissions

The following table lists the permissions supported under RBAC for Ripple. Ripple permissions belong to the `ripple` namespace.

| Permission | Description |
| :--- | :--- |
| `Admin` | No restrictions. Root user, by default, has this permission. |
| `ReadSettings` | View global Ripple settings only. |
| `ModifySettings` | Allowed to modify global Ripple settings. |
| `ReadInvoiceSettings` | View invoice settings only. |
| `ModifyInvoiceSettings` | Allowed to modify invoice settings. |
| `ReadBillingGroup` | View billing group only. |
| `ModifyBillingGroup` | Allowed to modify billing group settings. |
| `ReadAccount` | View account section only. |
| `ModifyAccount` | Allowed to modify account section settings. |
| `ReadReseller` | View reseller section only. |
| `ModifyReseller` | Allowed to modify reseller section settings. |
| `ReadInvoice` | View invoice section only. |
| `ModifyInvoice` | Allowed to modify invoice section settings. |
| `ReadRi` | View RI section only. |
| `ModifyRi` | Allowed to modify RI section settings. |

## Ocean permissions

{% hint style="warning" %}
This section is still a work in progress.
{% endhint %}

The following table lists the permissions supported under RBAC for Ocean. Ocean permissions belong to the `ocean` namespace.

| Permission | Description |
| :--- | :--- |
| `Admin` | No restrictions. Root user, by default, has this permission. |

## User permissions

The following table lists the permissions supported under user management. User permissions belong to the `user` namespace.

| Permission | Description |
| :--- | :--- |
| `Admin` | No restrictions. Root user, by default, has this permission. |
| `ReadOnly` | View user information, including API clients. |
| `ModifyUsers` | Allowed to modify user attributes. |
| `ModifyApiClients` | Allowed to modify API clients. |

