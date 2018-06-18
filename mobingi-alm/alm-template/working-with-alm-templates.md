# Working with ALM Templates

## ALM Template formats {#template-formats}

ALM Template is designed in JSON format. You can also write your template in YAML format and then convert it into JSON file when you deploy your stacks on ALM UI \(or through CLI, or API\).

{% hint style="info" %}
Official YAML format support is in-progress.
{% endhint %}

## ALM Template components {#template-components}

ALM Template top-level components consist of `version`, `label`, `description`, `vendor`, `configurations`.

### version {#template-components-version}

The version of ALM Template release. This value is always **2017-03-03**.

### label {#template-components-label}

The label of the ALM Template. You can use this section to mark the labels for each of your ALM Template versions. This is useful when you update your template. This value can be empty, and you can write up to 64 characters in length.

### description {#template-components-description}

The description of the ALM Template. You can use this section to describe the purpose of the ALM Template. For example: production app stack. This value can be empty, and you can write up to 255 characters in length.

### vendor {#template-components-vendor}

The cloud platform vendor of which the template will be deployed to. You need to specify the vendor in every ALM Template you write, and can only specify one vendor at a time.

### configurations {#template-components-configurations}

The configurations of the stack which ALM Template is about to deploy. In the configurations section, you specify one or multiple configuration layers of your application's provision and container runtime settings. Inside each layer, there are four sections you need to specify:

* **role**

  The "role" of which the stack layer defines to.

  You deploy multiple layers within one ALM Template, for example two _web_ layers, one _bastion_ layer and one _database_ layer. The current available role names:

  * `web`
  * `bastion`

* **flag**

  The unique identifier of each layer.

  You must specify the _flag_ name for each configuration layer. The value must between 4 to 18 characters in length and contains only alphanumeric characters.

* **provision**

  The infrastructure provisioning configurations.

  For more information on _provision_ section, please refer to [ALM Template Reference guide](https://docs.mobingi.com/mobingi-alm/alm-template/alm-template-reference).

* **container**

  The software runtime configurations _\(defined as docker images\)_ and code deployment requirement for each instance node.

  For more information on _container_ section, please refer to [ALM Template Reference guide](https://docs.mobingi.com/mobingi-alm/alm-template/alm-template-reference).

## ALM Template Structure {#template-structure}

Below is a tree view of all possible components within an ALM Template. The following structure is not a working demo template, but rather to explain all possible key names that may contain in the template body. For ALM Template examples, please refer to [Example ALM Templates](https://docs.mobingi.com/mobingi-alm/alm-template/example-alm-templates).

```yaml
version: string
label: string
description: string
vendor: object
  aws: object
  azure: object
  gcp: object
  alicloud: object
  k5: object
configurations: array of objects
  role: string
  flag: string
  provision: object
    vpc_id: string
    availability_zone: string
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
  container: object
    container_image: string
    container_registry_username: string
    container_registry_password: string
    container_code_dir: string
    container_code_repo: string
    container_git_reference: string
    container_git_private_key: string
    container_ports: array of numbers
    container_users: object
    container_env_vars: object
```

