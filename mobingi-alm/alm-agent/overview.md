# Overview

## What is ALM-agent? <a id="what-is-alm-agent"></a>

The ALM-agent is software for Mobingi ALM. ALM-agent is the primary component of container management.

ALM-agent runs on instances, manages Docker containers and deploys code to instances on behalf of you.

ALM-agent works with [ALM Template](https://docs.mobingi.com/mobingi-alm/alm-template/what-is-alm-template). When you run the ALM-agent, the agent on the instance processes the ALM Template and configures the instance as specified.

## Characteristics of ALM Agent <a id="characteristics-of-alm-agent"></a>

The ALM-agent is a tool for managing container and continuous deployment for your application. It provides several key features:

* Container Management
  * ALM-agent can manage container lifecycle \(create container, start or stop container, renew container image, deploy application code and manage log containers, etc.\).
* Blue-Green Deployment using Container
  * ALM-agent uses Blue-Green Deployment to achieve zero-downtime deployment of your application code.
* Health Checking
  * ALM-agent checks not only the instance status but also the container status.
* Multi Cloud
  * ALM-agent can run at any Cloud Service such as AWS, Alibaba Cloud, Azure, GCP, Fujitsu K5, etc.

