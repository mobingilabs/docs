# Overview

{% hint style="info" %}
This product is already deprecated.
{% endhint %}

Ocean is Mobingi's product for end-to-end application lifecycle management, including infrastructure provisioning, application deployment, and monitoring in a multi-cloud environment.

You can do deployments in Ocean using Ocean templates. One template is equivalent to one deployment. You can define applications and stacks in a template. Applications are container-based. Stacks are the infrastructure definitions where you can deploy your applications. Ocean uses [Kubernetes](https://kubernetes.io/) as its default infrastructure for application deployment.

Ocean deploys your infrastructure and your applications to your cloud account, whether it's AWS, Azure, Alibaba Cloud or GCP. You need to register your cloud credentials to Ocean before you start deploying templates.

## Vendor codes

| Provider | Vendor code |
| :--- | :--- |
| Alibaba Cloud | `alicloud` |
| Amazon Web Services \(AWS\) | `aws` |
| Microsoft Azure | `azure` |
| Google Cloud Platform | `gcp` |

These codes are used in [Ocean templates](https://docs.mobingi.com/v/ocean-en/reference-2018-07-02), as well as in API requests and responses, if any.

