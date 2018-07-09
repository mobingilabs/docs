# Reference \(2018-07-02\)

{% hint style="info" %}
We are in the process of updating the current template to a new version suited for multi-application, multi-stack, and multi-vendor deployments. It will be a YAML-based template \(although JSON is also supported\). We will be releasing these new features in the coming months. Stay tuned!
{% endhint %}

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
  - string # name of stack definition(s)

# stack definitions
stacks:
- name: string
  labels:
  - key: string
    value: string
  vendors:
  - string
  regions:
  - region: string
    availability_zones:
    - string
  vpc_group: string
  instance_group: string
  keypair: boolean
  security_group: string
  load_balancer:
    lb_type: string
    scheme: string
    security_groups:
    - string
    subnets:
    - string
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
  k8s: {tbd}
  
# The following section (groups) can be customizable although
# Mobingi will provide common definitions that can be referenced
# by name.

# -- start --

# instance group definitions
instance_groups:
- name: string
  vendors:
  - name: string # not a reference to 'vendors'
    instance_type: string
    image: string
    instance_count: number
    volume_type: string
    volume_size: number
    
# virtual network group definitions
# aws: vpc
# azure: vnet
# gcp: vpc
vpc_groups:
- name: string
  # vendor-independent
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
  - name: string # not a reference to 'vendors'
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
- name: string
  # vendor-independent
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
  - name: string # not a reference to 'vendors'
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
      
# -- end --
      
# vendor definitions
vendors:
- name: string # could be an entry in safebox
  provider: string
```

