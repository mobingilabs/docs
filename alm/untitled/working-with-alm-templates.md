# Working with ALM Templates

## Alm-template Formats {#template-formats}

Alm-template is designed in **Json** format. You can also write your template in Yaml format and then convert it into json file when you deploy your stacks on ALM UI \(or through CLI, API\).

_Official yaml format support is in-progress_

## Alm-template Components {#template-components}

Alm-template top-level components consist of `version`, `label`, `description`, `vendor`, `configurations`.

### - version {#template-components-version}

The version of Alm-template release.

This value is always _2017-03-03_.

### - label {#template-components-label}

The label of the Alm-template.

You can use this section to mark the labels for each of your alm-template versions. This is useful when you update your template.

This value can be empty, and you can write up to 64 characters in length.

### - description {#template-components-description}

The description of the Alm-template.

You can use this section to describe the purpose of the alm-template, _for example: production app stack_.

This value can be empty, and you can write up to 255 characters in length.

### - vendor {#template-components-vendor}

The cloud platform vendor of which the template will be deployed to.

You need to specify the vendor in every alm-template you write, and can only specify one vendor at a time.

### - configurations {#template-components-configurations}

The configurations of the stack which Alm-template about to deploy.

In the configurations section, you specify one or multiple configuration layers of your application's provision and container runtime settings.

Inside each layer, there are four sections you need to specify:

* **role**

  The "role" of which the stack layer defines to.

  You deploy multiple layers within one Alm-template, for example two _web_ layers, one _bastion_ layer and one _database_ layer. The current available role names:

  * `web`
  * `bastion`

* **flag**

  The unique identifier of each layer.

  You must specify the _flag_ name for each configuration layer. The value must between 4 to 18 characters in length and contains only alphanumeric characters.

* **provision**

  The infrastructure provisioning configurations.

  For more information on _provision_ section, please refer to [ALM Template Reference guide](https://learn.mobingi.com/alm-templates-reference#provision).

* **container**

  The software runtime configurations _\(defined as docker images\)_ and code deployment requirement for each instance node.

  For more information on _container_ section, please refer to [ALM Template Reference guide](https://learn.mobingi.com/alm-templates-reference#container).

## Alm-template Structure {#template-structure}

Below is a tree view of all possible components within an alm-template.

The following structure is not a working demo template, but rather to explain all possible key names that may contain in the template body.

For Alm-template examples, please refer to [Example ALM Templates](https://learn.mobingi.com/alm-templates-example-templates).

* versionstring
* labelstring
* descriptionstring
* vendorobject
  * awsobject
    * credstring
    * secretstring
    * regionstring
  * alicloudobject
    * credstring
    * secretstring
    * regionstring
  * k5object
    * credstring
    * regionstring
* configurationsarray of objects
  * rolerole name
  * flagflag name
  * provisionprovision configuration
    * vpc\_idstring
    * availability\_zonestring
    * instance\_typestring
    * imagestring
    * instance\_countnumber
    * volume\_typestring
    * volume\_sizenumber
    * keypairboolean
    * subnetobject
      * cidrstring
      * publicboolean
      * auto\_assign\_public\_ipboolean
    * security\_groupobject
      * ingressarray of objects
      * cidr\_ipstring
      * from\_portnumber
      * ip\_protocolstring
      * to\_portnumber
      * egressarray of objects
      * cidr\_ipstring
      * from\_portnumber
      * ip\_protocolstring
      * to\_portnumber
    * network\_aclarray of objects
      * rule\_numbernumber
      * protocolstring
      * rule\_actionstring
      * acl\_egressboolean
      * cidrstring
    * load\_balancerobject
      * lb\_typestring
      * schemestring
      * subnetsstring
      * security\_groupsstring
      * listenersarray of objects
      * load\_balancer\_portstring
      * protocolstring
      * instance\_portstring
      * instance\_protocolstring
      * cert\_domainstring
      * health\_checkobject
      * healthy\_thresholdstring
      * intervalstring
      * targetstring
      * timeoutstring
      * unhealthy\_thresholdstring
    * auto\_scalingobject
      * minnumber
      * maxnumber
      * spot\_minnumber
      * spot\_maxnumber
      * cooldownstring
      * healthcheck\_grace\_periodstring
      * availability\_zonesstring
  * containerruntime configuration
    * container\_imagestring
    * container\_registry\_usernamestring
    * container\_registry\_passwordstring
    * container\_code\_dirstring
    * container\_git\_repostring
    * container\_git\_referencestring
    * container\_git\_private\_keystring
    * container\_portsarray of numbers
    * container\_usersobject
    * container\_env\_varsobject

