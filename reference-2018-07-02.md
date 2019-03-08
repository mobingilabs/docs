# Reference \(2018-07-02\)

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

The following is the proposed new version of ALM Template. By default, all keys are optional unless stated otherwise.

```yaml
---
version: 20180702 # required

# Name should be unique across your account.
name: deployment1

description: string

---
credentials:
# The name of the credential to use. This credential should already
# be registered to your Mobingi account. 
- name: mycreds

  # Valid values:
  # - aws
  # - gcp
  # - azure
  # - alicloud
  provider: aws

---
# The list of applications to be deployed.
applications:
# The name of the application to deploy. Should be unique at
# deployment level.
- name: app1

  # TODO: Mobingi-defined keys here. For sane defaults, and if
  # you don't like writing k8s yaml files.

  # Use this key if you want to deploy raw Kubernetes apps to
  # your stack. All k8s resources are supported here.
  k8sExtra: |
    {Insert Kubernetes application deployments here}
    
  # The list of stacks where you want to deploy this application.
  # The following names should correspond to a cluster under the
  # `stacks` key.
  stacks:
  - cluster1
  
---
# The list of stacks where you want to deploy your applications.
stacks:
#  Stack name should be unique at deployment level
- name: cluster1

  # For now, only k8s clusters are supported.
  type: k8s
  
  # This should correspond to a credential name you provided
  # somewhere in this template.
  credential: mycreds
  
  # Region values depends on what cloud this stack belongs.
  region: ap-northeast-1
  
  # Applies to k8s master only. Behaviour may change depending on
  # cloud provider.
  highlyAvailable: false
  
  # Definitions of worker node groups for this cluster.
  workerGroups:
  # Cloud provider specific instance type.
  - type: t2.medium
  
    # Node autoscaling minimum and maximum values.
    min: 3
    max: 10
    
    # If true, this node group will use the cloud provider's low-cost
    # instances, i.e. Spot (AWS), Preemptive (GCP), Low priority (Azure), etc.
    lowCost: bool
    
  # So far, all key-values above are Mobingi-defined defaults for a k8s cluster.
  # Set this to true if you want to skip provisioning the cluster defined above.
  skip: bool
  
  # This key is provided if you want to provision any AWS resources using
  # CloudFormation.
  cfnExtra: |
    {Insert CloudFormation template here}
    
  # This key is provided if you want to provision any GCP resources using
  # Deployment Manager.
  dmExtra: |
    {Insert GCP Deployment Manager template here}
    
  # This key is provided if you want to provision any Azure resources using
  # Azure Resource Manager.
  armExtra: |
    {Insert Azure Resource Manager template here}
```

