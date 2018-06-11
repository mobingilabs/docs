# Custom installation script

When Mobingi installs a container, it performs a series of steps to start up a webserver. During these steps you can insert your code in the form of a bash shell script to perform the installation and configuration you need.

![](../../.gitbook/assets/custom-script.png)

Simply add a `mobingi-init.sh` file to the **root** directory of your code and the container will run the instructions in the script to perform the additional setup required by your webserver.

**Example Script:**  
Below is a sample script for a project coded in PHP and requires Composer, this script will automatically setup the environment.

```bash
sudo apt-get update
sudo apt-get -y install curl
sudo su
curl -sS https://getcomposer.org/installer | php
php composer.phar install
```

And you are able to view the logs through application's details page, click on the Logs tab, and select on the instance id, then choose moDaemon or Startup from the drop down menu to view service logs.

![](../../.gitbook/assets/custom-script2.png)

