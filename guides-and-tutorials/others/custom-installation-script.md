# Custom installation script

When Mobingi installs a container, it performs a series of steps to start up a webserver. During these steps you can insert your code in the form of a bash shell script to perform the installation and configuration you need.

![](../../.gitbook/assets/custom-script.png)

Simply add a `mobingi-init.sh` file to the **root** directory of your code and the container will run the instructions in the script to perform the additional setup required by your webserver.

**Example Script:**  
Below is a sample script for a project coded in PHP and requires Composer, this script will automatically setup the environment.

```text
sudo apt-get updatesudo apt-get -y install curlsudo sucurl -sS https://getcomposer.org/installer | phpphp composer.phar install
```

