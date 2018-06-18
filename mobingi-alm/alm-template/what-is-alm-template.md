# What is ALM Template?

## Concepts {#concepts}

* ALM Template is a JSON-formatted configuration file which defines your cloud-native application's architecture design and runtime configuration.
* ALM Template is cloud platform agnostic. You write your template once and it works on any cloud platforms such as AWS, GCP, Azure, AliCloud, etc.
* You can save and reuse ALM Templates at anytime.

## How does it work {#how-does-it-work}

ALM Template is a component of [ALM](https://mobingi.com/how-mobingi-alm-works). You write your ALM Template in code blocks and paste it on ALM console \(or through CLI, or API\) and it will be converted into each cloud platform's native configuration standards, then ALM will provision all resources on your behalf.

If you specify the runtime configurations of your application in the `container` section of the ALM Template, then ALM will also deploy an [ALM-agent](https://docs.mobingi.com/mobingi-alm/alm-agent) on each provisioned node to perform application runtime setup and continuous code deployment.



