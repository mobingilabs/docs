# ALM Template Language

ALM Template provides several built-in functions that help you manage your ALM Template. These functions are named **ATL**, short for **A**LM **T**emplate **L**anguage. Not to be confused with Microsoft's [ATL](https://msdn.microsoft.com/en-us/library/3ax346b7.aspx).

Use ATL functions in your templates to assign values to properties that are not available until runtime.

{% hint style="info" %}
For now, ATL is only supported in AWS. Support for other cloud vendors will be available soon.

You can use ATL functions only in specific parts of a template. Please refer to each functions' document for detailed explanation.
{% endhint %}

## computed {#computed}

_Usage:_

`${computed}`

This function is used to calculate the valid value for supported declarative in your ALM Template.

Example:

```javascript
  "instance_type": "${computed}"
```

## use {#use}

_Usage:_

`${use( .. )}`

This function is used to reference the value that you defined in other declarative already.

_Example:_

```javascript
  "availability_zones": "${use(Layer1.provision.availability_zone),use(Layer2.provision.availability_zone)}"
```

**Note:** This function can only be used if the origin value is type of _string_, it cannot be applied to any other type of values. For referencing values such as object or array, you use `${copy( .. )}`.

## copy {#copy}

_Usage:_

`${copy( .. )}`

This function is used to copy the whole value that you defined in other declarative already.

_Example:_

```javascript
  "security_group": "${copy(Layer1.provision.security_group)}"
```

## ref {#ref}

_Usage:_

`#ref( .. )`

Currently, this function can be used only in:

1. load\_balancer : security\_groups

   ```javascript
    "load_balancer": {
        "security_groups": "#ref(Layer2.provision.security_group)",
    },
   ```

   _Use case explanation:_

   When the load balancer requires specified security groups, you can use this function to reference the security groups that are defined in `security_group` declarative.

## share {#share}

Usage:

`#share( .. )`

Currently, this function can be used in two declarative:

1. load\_balancer : subnets

   ```javascript
    "load_balancer": {
        "subnets": "#share(Layer1.provision.subnet,Layer2.provision.subnet)",
    },
   ```

   _Use case explanation:_

   When you deploy an _application_ or _networking_ load balancer on AWS, by default each load balancer requires at least two subnets, so you use this function to define the target subnets which will be used by this load balancer.

2. auto\_scaling

   ```javascript
    {
        "auto_scaling": "#share(Layer1.provision.auto_scaling)"
    }
   ```

   _Use case explanation:_

   When you register multiple load balancers to the instances that are in the same auto scaling group, you use this function to define the target auto scaling group which will be shared with this load balancer.

