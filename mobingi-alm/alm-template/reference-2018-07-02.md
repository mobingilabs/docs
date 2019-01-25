# Reference \(2018-07-02\)

{% hint style="info" %}
We are in the process of updating the current template to a new version suited for multi-application, multi-stack, and multi-vendor deployments. It will be a YAML-based template \(although JSON is also supported\). We will be releasing these new features in the coming months. Stay tuned!
{% endhint %}

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
  # For now, only AWS is supported in this new template.
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
    apiVersion: apps/v1
    kind: Deployment
    metadata:
      name: hello1
    spec:
      selector:
        matchLabels:
          app: hello1
      replicas: 1
      revisionHistoryLimit: 5
      template:
        metadata:
          labels:
            app: hello1
        spec:
          containers:
          - name: hello1
            image: hashicorp/http-echo
            args: ["-text=Hello world (1)"]
            resources:
              requests:
                cpu: 100m
                memory: 300Mi
            imagePullPolicy: Always
            ports:
            - containerPort: 5678
    ---
    apiVersion: v1
    kind: Service
    metadata:
      name: hello1
    spec:
      type: NodePort
      ports:
      - protocol: TCP
        port: 80
        targetPort: 5678
      selector:
        app: hello1
  # The list of stacks where you want to deploy this application.
  # The following names should correspond to a cluster under the
  # `stacks` key.
  stacks:
  - cluster1
  # Example for multiple apps in a cluster.
- name: app2
  k8sExtra: |
    apiVersion: apps/v1
    kind: Deployment
    metadata:
      name: hello2
    spec:
      selector:
        matchLabels:
          app: hello2
      replicas: 1
      revisionHistoryLimit: 5
      template:
        metadata:
          labels:
            app: hello2
        spec:
          containers:
          - name: hello2
            image: hashicorp/http-echo
            args: ["-text=Hello world (2)"]
            resources:
              requests:
                cpu: 100m
                memory: 300Mi
            imagePullPolicy: Always
            ports:
            - containerPort: 5678
    ---
    apiVersion: v1
    kind: Service
    metadata:
      name: hello2
    spec:
      type: NodePort
      ports:
      - protocol: TCP
        port: 80
        targetPort: 5678
      selector:
        app: hello2
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
          TopicName: "cfnextra-sample-snstopic"`
  dmExtra: |
    {Insert GCP Deployment Manager template here}
  armExtra: |
    {Insert Azure Resource Manager template here}
```

