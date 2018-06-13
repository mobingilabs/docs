# What is RBAC?

RBAC is a policy document that formally states one or more permissions. To assign permissions to a user, you create a policy, which is a document that explicitly lists permissions.

## Concepts

### Create roles

* Create roles can be done by root account only. _\(Root account is the one you login using your email address.\)_
* Create roles action can be performed through CLI, API or UI.
* Editing roles is simple and straightforward. All users under your root account will be able to view their roles that assigned to them.

### Attach roles to users or teams

* Role can be created by root account only.
* Role can be assigned to _Users_ and _Teams._
* _Users_ or _Teams_ can be attached with one Role only.
* Roles assigned on _Team_ will overwrite the roles assigned on _User._

### End user effect

* When users login to Mobingi ALM dashboard \(or interacting through CLI or API\), roles that attached to them will be evaluated on every action request.
* If an action isn't granted by the role definition, such action will be denied.
* If an action is grated by the role definition, the action will be allowed.

