# Custom Docker containers

## Deploy custom Docker containers

It is possible to deploy your own docker container on mobingi ALM. Simply type in the name of your docker image on docker hub and you are ready to go.

{% hint style="info" %}
Docker images that are not modified to have a configuration file and container\_status files will not be able to take advantage of [Blue-Green Deployment](https://docs2.mobingi.com/v/v2/guides-and-tutorials/others/blue-green-deployment), and code deploys will write into the `/var/www` folder.
{% endhint %}

Mobingi ALM also automatically maps port 80 and 443 exposed by the container to the port 80 and 443 respectively on the machine. Other ports are ignored.  


## Configuration file

If a custom docker container does not have a configuration file, mobingi ALM will immediately switch new connections to the new container the moment it starts. If your docker container needs to perform certain tasks before it is able to start, it needs to signal that it is ready to accept connections.

Without a configuration file also, mobingi ALM will only deploy code into the `/var/www` folder.

In order to enable [Blue-Green Deployment](https://docs2.mobingi.com/v/v2/guides-and-tutorials/others/blue-green-deployment) and specify a specific folder for the code deploys to place code in, the container must have the following things:

* A config file in the root directory
* The startup command must write running into the `/var/log/container_status` file when it is ready to accept connections.

This is an example config file:

```text
{   "codeDirectory": "/srv/code"}
```

