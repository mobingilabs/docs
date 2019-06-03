# Overview

tbd 
Mobingi RBAC is a Mobingi-wide role-based access control system that provides fine-grained access management to Mobingi features and resources. In using Mobingi RBAC, you can grant only the amount of access to users that they need to perform their jobs.

Mobingi RBAC is defined around users, namespaces, roles, and permissions. Users can be actual users in your organization, or a virtual user used in scripts or automation codes. Roles are job functions or groups that have a certain level of authority, or a list of permissions attached to it. Examples are `Admin`, `Developers`, etc. You can assign up to five \(5\) roles to a user per namespace.

Roles and permissions in Mobingi RBAC are isolated based on namespaces. What this means is that a role can only be created under a specific namespace, with namespace-specific permissions attached to it.

Mobingi root users \(the main account you registered to Mobingi, in email address form\) are always super admins, or have unrestricted access across namespaces. Typically, root users should create subusers and assign specific roles to them.

