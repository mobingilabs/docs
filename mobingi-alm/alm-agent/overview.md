# Overview

## What is ALM-agent? {#what-is-alm-agent}

The ALM Agent is software for Mobingi ALM. ALM Agent is the primary component of container management.

ALM Agent runs on instances, manages Docker containers and deploys code to instances on behalf of you.

ALM Agent works with [ALM Template](https://docs.mobingi.com/mobingi-alm/alm-template/what-is-alm-template). When you run the ALM Agent, the agent on the instance processes the ALM Template and configures the instance as specified.

## Characteristics of ALM Agent {#characteristics-of-alm-agent}

The ALM Agent is a tool for managing container and continuous deployment for your application. It provides several key features:

* Container Management
  * ALM Agent can manage container lifecycle \(create container, start or stop container, renew container image, deploy application code and manage log containers, etc.\).
* Blue-Green Deployment using Container
  * ALM Agent uses Blue-Green Deployment to achieve zero-downtime deployment of your application code.
* Health Checking
  * ALM-agent checks not only the instance status but also the container status.
* Multi Cloud
  * ALM Agent can run at any Cloud Service such as Amazon Web Services, Alibaba Cloud, Fujitsu K5, etc.

