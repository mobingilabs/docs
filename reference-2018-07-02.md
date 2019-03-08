# Reference \(2018-07-02\)

{% hint style="warning" %}
This page is still a work in progress.
{% endhint %}

The following is the proposed new version of ALM Template. By default, all keys are optional unless stated otherwise.

```yaml
---
version: 20180702 # required
name: deployment1 # should be unique across account level
---
# These credentials should be registered to your ALM account.
credentials:
# The credential name you used to input the credential.
- name: subuser01
  # Valid values: aws, gcp, azure, alicloud
  provider: aws
---
# The list of applications to be deployed.
applications:
# The name of the application to deploy. Should be unique at
# deployment level.
- name: app1
  # TODO: Mobingi-defined keys here. For sane defaults, and if
  # you don't like writing k8s yaml files.
  ...
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
- name: cluster1 # should be unique at deployment level
  type: k8s # for now, only k8s clusters are supported
  # This should correspond to a credential name you provided
  # somewhere in this template.
  credential: subuser01
  region: ap-northeast-1 # cloud provider specific region
  keyPair: true
  # Applies to k8s master only.
  highlyAvailable: false
  # Applies to the k8s worker nodes. 
  workerGroups:
  - type: t2.medium # cloud provider specific instance type
    min: 3
    max: 10
  # Option to skip Mobingi-defined cluster.
  skip: false
  # This key is provided if you want to provision any AWS resources using
  # CloudFormation.
  cfnExtra: |
    # A CloudFormation template example:
    AWSTemplateFormatVersion: '2010-09-09'
    Description: 'AWS CloudFormation Sample CfnExtra'
    Resources:
      CfnExtraSnsTopic:
        Type: AWS::SNS::Topic
        Properties:
          TopicName: "cfnextra-sample-snstopic"
  # This key is provided if you want to provision any GCP resources using
  # Deployment Manager.
  dmExtra: |
    {Insert GCP Deployment Manager template here}
  # This key is provided if you want to provision any Azure resources using
  # Azure Resource Manager.
  armExtra: |
    {Insert Azure Resource Manager template here}
```

