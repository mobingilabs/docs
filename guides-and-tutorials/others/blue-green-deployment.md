# Blue-green deployment

Mobingi ALM uses Blue-Green Deployment to achieve zero-downtime deployment of new code. When you click deploy in the code page, it will simply deploy your code.

![](../../.gitbook/assets/bg-deploy1.png)

Whenever you click this button, mobingi ALM will initiate deployment on all your servers. It will:

1. Renew the container image
2. Download the code from the repository
3. Create a new container
4. Perform code installation on the container
5. Test the container
6. If successful, direct all new incoming connections to the new container
7. Delete the old container after ten seconds

Firstly, all connections are being sent to the existing container, known as the Blue Container.

![](../../.gitbook/assets/bg-deploy2.png)

When code is deployed, a new Green Container containing the new code is started up and the installation process begins inside it.  


![](../../.gitbook/assets/bg-deploy3.png)

Once it is ready, all traffic is then redirected to this new container. While existing connections continue to stay open against the old Blue Container.

![](../../.gitbook/assets/bg-deploy4.png)

After 10 seconds, which is enough for most HTTP requests to complete, the Blue Container is shut down, and the Green Container will be considered the Blue Container for the next deployment.

![](../../.gitbook/assets/bg-deploy5.png)

