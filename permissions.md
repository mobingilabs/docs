{% hint style="warning" %} This is still a draft version. {% endhint %}

# Permissions

The following tables list all supported permissions under Mobingi RBAC across all namespaces.

- The permissions are hierarchical. Any user with permissions in the higher hierarchy will have permissions in the lower hierarchy as well. For example, `Admin` will have all permissions in the respective namespace.
- Some permissions can have resources filter. Empty filter will mean all resources allowed. Resources filter also follow the same hierarchical logic and only `Allow` effect is supported as of now.

## RBAC permissions

The following table lists the permissions supported under RBAC management. RBAC permissions belong to the `rbac` namespace.

| Permission                          | Description                                                  | Resources Supported |
| ----------------------------------- | ------------------------------------------------------------ | ------------------- |
| <nobr>`Admin`</nobr>                | No restrictions. Root user, by default, has this permission. |                     |
| <nobr>`\|__ ModifyRoles`</nobr>     | Allowed to modify RBAC roles.                                |                     |
| <nobr>`\|__ ModifyUserRoles`</nobr> | Allowed to modify user-role mappings.                        |                     |
| <nobr>`\|____ ReadOnly`</nobr>      | View RBAC permissions, roles, and mappings.                  |                     |

## Wave permissions

The following table lists the permissions supported under RBAC for Wave. Wave permissions belong to the `wave`</nobr> namespace.

| Permission                                | Description                                                  | Resources Supported |
| ----------------------------------------- | ------------------------------------------------------------ | ------------------- |
| <nobr>`Admin`</nobr>                      | No restrictions. Root user, by default, has this permission. |                     |
| <nobr>`\|-- ReadAccount`</nobr>           | View account list only.                                      | Accounts            |
| <nobr>`\|-- ModifyAccountSettings`</nobr> | Allowed to modify account level settings.                    | Accounts            |
| <nobr>`\|---- ReadAccountSettings`</nobr> | View account level settings only.                            | Accounts            |
| <nobr>`\|-- DownloadBulk`</nobr>          | Allowed to download bulk CSV.                                |                     |
| <nobr>`\|-- ModifyGroups`</nobr>          | Allowed to modify groups.                                    | Account groups      |
| <nobr>`\|---- ReadGroups`</nobr>          | View groups only.                                            | Account groups      |
| <nobr>`\|-- ReadInvoice`</nobr>           | View invoices only                                           |                     |
| <nobr>`\|-- ReadRi`</nobr>                | View RIs only                                                |                     |
| <nobr>`\|-- ReadSavingsPlan`</nobr>       | View savings plan only                                       |                     |
| <nobr>`\|-- ModifySettings`</nobr>        | Allowed to modify global Wave settings.                      |                     |
| <nobr>`\|---- ReadSettings`</nobr>        | View global Wave settings only.                              |                     |
| <nobr>`\|-- ModifyTags`</nobr>            | Allowed to modify tags.                                      |                     |
| <nobr>`\|---- ReadTags`</nobr>            | View tags only.                                              |                     |

## Ripple permissions

The following table lists the permissions supported under RBAC for Ripple. Ripple permissions belong to the `ripple` namespace.

| Permission                                     | Description                                                  | Resources Supported |
| ---------------------------------------------- | ------------------------------------------------------------ | ------------------- |
| <nobr>`Admin`</nobr>                           | No restrictions. Root user, by default, has this permission. |                     |
| <nobr>`\|-- ModifyBillingGroup`</nobr>         | Allowed to modify billing group settings.                    | Billing groups      |
| <nobr>`\|---- ReadBillingGroup`</nobr>         | View billing group only.                                     | Billing groups      |
| <nobr>`\|------ ModifyAccount`</nobr>          | Allowed to modify account section settings.                  | Billing groups      |
| <nobr>`\|-------- ReadAccount`</nobr>          | View account section only.                                   | Billing groups      |
| <nobr>`\|------ ModifyInvoice`</nobr>          | Allowed to modify invoice section settings.                  | Billing groups      |
| <nobr>`\|-------- ReadInvoice`</nobr>          | View invoice section only.                                   | Billing groups      |
| <nobr>`\|------ ModifyInvoiceSettings`</nobr>  | Allowed to modify invoice settings.                          | Billing groups      |
| <nobr>`\|--------- ReadInvoiceSettings`</nobr> | View invoice settings only.                                  | Billing groups      |
| <nobr>`\|------ ModifyReseller`</nobr>         | Allowed to modify reseller section settings.                 | Billing groups      |
| <nobr>`\|-------- ReadReseller`</nobr>         | View reseller section only.                                  | Billing groups      |
| <nobr>`\|-- ModifyCustomField`</nobr>          | Allowed to modify custom field settings.                     |                     |
| <nobr>`\|---- ReadCustomField`</nobr>          | View custom field settings.                                  |                     |
| <nobr>`\|-- ModifyCustomService`</nobr>        | Allowed to modify custom services settings.                  |                     |
| <nobr>`\|---- ReadCustomService`</nobr>        | Read custom service settings only.                           |                     |
| <nobr>`\|-- ModifyInvoiceTemplate`</nobr>      | Allowed to modify invoice templates.                         |                     |
| <nobr>`\|---- ReadInvoiceTemplate`</nobr>      | View invoice templates only.                                 |                     |
| <nobr>`\|-- ModifyOriginalCost`</nobr>         | Allowed to modify original cost settings.                    |                     |
| <nobr>`\|---- ReadOriginalCost`</nobr>         | Read original cost only                                      |                     |
| <nobr>`\|-- ModifyProject`</nobr>              | Allowed to modify projects.                                  |                     |
| <nobr>`\|---- ReadProject`</nobr>              | Read projects only.                                          |                     |
| <nobr>`\|-- ReadReport`</nobr>                 | Read reports only.                                           |                     |
| <nobr>`\|-- ModifyRi`</nobr>                   | Allowed to modify RI section settings.                       |                     |
| <nobr>`\|---- ReadRi`</nobr>                   | View RI section only.                                        |                     |
| <nobr>`\|-- ReadSavingsPlan`</nobr>            | Read savings plan only.                                      |                     |
| <nobr>`\|-- ModifySettings`</nobr>             | Allowed to modify global Ripple settings.                    |                     |
| <nobr>`\|---- ReadSettings`</nobr>             | View global Ripple settings only.                            |                     |
| <nobr>`\|-- ModifyTags`</nobr>                 | Allowed to modify tags.                                      |                     |
| <nobr>`\|---- ReadTags`</nobr>                 | View tags only.                                              |                     |

## User permissions

The following table lists the permissions supported under user management. User permissions belong to the `user` namespace.

| Permission                      | Description                                                  | Resources Supported |
| ------------------------------- | ------------------------------------------------------------ | ------------------- |
| <nobr>`Admin`</nobr>            | No restrictions. Root user, by default, has this permission. |                     |
| <nobr>`\|-- ModifyUsers`</nobr> | Allowed to modify user attributes.                           |                     |
| <nobr>`\|---- ReadOnly`</nobr>  | View user information, including API clients.                |                     |
