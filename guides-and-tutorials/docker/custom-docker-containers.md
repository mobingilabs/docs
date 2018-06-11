# Custom Docker containers

## Deploy custom Docker containers

It is possible to deploy your own docker container on mobingi ALM. Simply type in the name of your docker image on docker hub and you are ready to go.

{% hint style="info" %}
Docker images that are not modified to have a configuration file and container\_status files will not be able to take advantage of [Blue-Green Deployment](https://docs.mobingi.com/official/guide/bg-deploy), and code deploys will write into the `/var/www` folder.
{% endhint %}

