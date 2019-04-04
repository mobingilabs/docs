---
description: Mobingi Documentation
---

# Overview

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

## User permissions

The following are the list of permissions supported in user management. User permissions belongs to the `user` namespace.

| Permission | Description |
| :--- | :--- |
| `Admin` | No restrictions. Root user, by default, has this permission. |
| `ReadOnly` | View user information, including API clients. |
| `ModifyUsers` | Allowed to modify user attributes. |
| `ModifyApiClients` | Allowed to modify API clients. |

## RBAC permissions

The following are the list of permissions supported in RBAC management. RBAC permissions belongs to the `rbac` namespace.

| Permission | Description |
| :--- | :--- |
| `Admin` | No restrictions. Root user, by default, has this permission. |
| `ReadOnly` | View RBAC permissions, roles, and mappings. |
| `ModifyRoles` | Allowed to modify RBAC roles. |
| `ModifyUserRoles` | Allowed to modify user-role mappings. |

## Wave permissions

The following are the list of permissions supported in RBAC for Wave. Wave permissions belongs to the `wave` namespace.

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
| `ReadBillingGroup` | View billing group dashboard data (graph) only. |
| `ModifyBillingGroup` | Allowed to modify billing group dashboard data. |

## Ripple permissions

The following are the list of permissions supported in RBAC for Ripple.

| Permission | Description |
| :--- | :--- |
| `Admin` | No restrictions. Root user, by default, has this permission. |

## Ocean permissions

The following are the list of permissions supported in RBAC for Ocean.

| Permission | Description |
| :--- | :--- |
| `Admin` | No restrictions. Root user, by default, has this permission. |

