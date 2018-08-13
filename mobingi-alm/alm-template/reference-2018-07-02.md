# Reference \(2018-07-02\)

{% hint style="info" %}
We are in the process of updating the current template to a new version suited for multi-application, multi-stack, and multi-vendor deployments. It will be a YAML-based template \(although JSON is also supported\). We will be releasing these new features in the coming months. Stay tuned!
{% endhint %}

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

The following is the proposed new version of ALM Template. By default, all keys are optional unless stated otherwise.

```yaml
version: string # '2018-07-02', required
label: string
description: string

# Definitions for apps that are to be deployed to one or more stacks.
# You can define 0 or more apps.
applications:
- name: string # required
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
  # List of stacks this app will be deployed to.
  - string

# Stack definitions. At least one (1) stack is required per template.
stacks:
- name: string # required
  labels:
  - key: string
    value: string
  vendors:
  - string # at least one (1) vendor is required
  region_groups: string
  vpc_group: string
  instance_group: string
  security_group: string
  load_balancer:
    lb_type: string
    scheme: string
    listeners:
    - load_balancer_port: string
      protocol: string
      instance_port: string
      instance_protocol: string
      cert_domain: string
    health_check:
      healthy_threshold: string
      interval: string
      target: string
      timeout: string
      unhealthy_threshold: string
  auto_scaling:
    min: number
    max: number
    spot_to_ondemand_ratio: number
    cooldown: string
    healthcheck_grace_period: string
  rdb:
    db_instance_type: string
    engine: string
    version: string
    storage: int
    multi_az: boolean
    replica: number
  k8s_group: string

# Vendor definitions.
vendors:
- name: string # required
  provider: string # required
  cred_name: string # required
  project_id: string # gcp only
  app_id: string # azure only
  subscription_id: string # azure only
  directory_id: string # azure only
  contract_number: string # fujitsu k5
  
# The following section (groups) can be customized although Mobingi
# will provide common definitions that can be referenced
# by name.

# region/az group definitions
region_groups:
- name: string # required
  vendors:
  - name: string # required
    region: string
    availability_zones:
    - string

# instance group definitions
instance_groups:
- name: string # required
  vendors:
  - name: string # required, not a reference to 'vendors'
    instance_type: string
    image: string
    instance_count: number
    volume_type: string
    volume_size: number
    keypair: boolean
    
# virtual network group definitions
# aws: vpc
# azure: vnet
# gcp: vpc
vpc_groups:
- name: string # required
  # vendor-independent subnet
  subnet:
    cidr: string
    public: boolean
    auto_assign_public_ip: boolean
    route: {tbd}
    network_acl:
      rule_number: number
      protocol: string
      rule_action: string
      acl_egress: boolean
      cidr_block: string
  vendors:
  - name: string # required, not a reference to 'vendors'
    subnet:
      cidr: string
      public: boolean
      auto_assign_public_ip: boolean
      route: {tbd}
      network_acl:
        rule_number: number
        protocol: string
        rule_action: string
        acl_egress: boolean
        cidr_block: string
        
# network security definitions
# aws: security groups
# azure: network security groups
# gcp: firewall
network_security_groups:
- name: string # required
  # vendor-independent ingress/egress
  ingress:
  - cidr: string
    from_port: number
    ip_protocol: string
    to_port: number
  egress:
  - cidr: string
    from_port: number
    ip_protocol: string
    to_port: number
  vendors:
  - name: string # required, not a reference to 'vendors'
    ingress:
    - cidr: string
      from_port: number
      ip_protocol: string
      to_port: number
    egress:
    - cidr: string
      from_port: number
      ip_protocol: string
      to_port: number
      
# kubernetes definitions
k8s_groups:
- name: string # required
  vendors:
  - name: string # required, not a reference to 'vendors'
    # 'gcp_native' can be the same as the following GCP resource:
    # https://cloud.google.com/kubernetes-engine/docs/references/rest/v1/projects.zones.clusters
    # If you provide 'gcp_native', all other keys (except 'name'),
    # will be overruled.
    gcp_native: object
```

