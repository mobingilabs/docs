# Reference \(2018-07-02\)

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

The following is the proposed new version of ALM Template.

```yaml
version: string # '2018-07-02'
label: string
description: string

# application definitions
applications:
- name: string
  labels:
  - key: string
    value: string
  container_image: string
  container_registry_username: string
  container_registry_password: string
  container_code_dir: string
  container_code_repo: string
  container_git_reference: string
  container_git_private_key: string
  container_ports:
  - number
  container_users: object
  container_env_vars:
  - key: string
    value: string
  stacks:
  - string

# stack definitions
stacks:
- name: string
  labels:
  - key: string
    value: string
  vendors:
  - string
  vpc_id: string
  region: string
  availability_zones:
  - string
  instance_type: string
  image: string
  instance_count: number
  volume_type: string
  volume_size: number
  keypair: boolean
  subnet: object
  security_group: object
  network_acl: object
  load_balancer: object
  auto_scaling: object

# vendor definitions
vendors:
- name: string
  provider: string
```

