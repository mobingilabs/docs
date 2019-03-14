# Reference \(v20180702\)

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

The following is the proposed version of Ocean Template. By default, all keys are optional unless stated otherwise.

```yaml
---
version: 20180702 # required

# Required. Name should be unique across your account.
name: string

description: string

---
credentials:
# Required. The name of the credential to use. This credential should already
# be registered to your Mobingi account.
- name: string

  # Valid values:
  #   aws
  #   gcp
  #   azure
  #   alicloud
  provider: string

---
# The list of applications to be deployed.
applications:
# Required. The name of the application to deploy. Should be unique at
# deployment level.
- name: string

  # Valid values (for now):
  #   deployment - Kubernetes deployment
  type: string

  # Number of initial container instances to run.
  replicas: number

  # Application autoscaling minimum and maximum.
  min: number
  max: number

  # Containers to run in this application.
  containers:
  - name: string
    image: string
    envVars:
    - key: string
      value: string
    ports:
    - number

  # So far, all key-values above are Mobingi-defined defaults for an application.
  # Set this to true if you want to skip deploying the application above.
  skip: bool

  # Use this key if you want to deploy raw Kubernetes apps to
  # your stack. All k8s resources are supported here.
  k8sExtra: |
    {Insert Kubernetes application deployments here}

  # The list of stacks where you want to deploy this application.
  # The following names should correspond to a cluster under the
  # `stacks` key.
  stacks:
  - string

---
# The list of stacks where you want to deploy your applications.
stacks:
#  Required. Stack name should be unique at deployment level
- name: string

  # Valid values (for now:
  #   k8s
  type: string

  # This should correspond to a credential name you provided
  # somewhere in this template.
  credential: string

  # Region values depends on what cloud this stack belongs.
  region: string

  # Applies to k8s master only. Behaviour may change depending on
  # cloud provider.
  highlyAvailable: bool

  # Definitions of worker node groups for this cluster.
  workerGroups:
  # Cloud provider specific instance type, i.e. t2.medium
  - type: string

    # Node autoscaling minimum and maximum values.
    min: number
    max: number

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
    
  # This key is provided if you want to provision any Alibaba resources using
  # Resource Orchestration Service.
  aliExtra: |
    {Insert Alibaba ROS template here}
```



