# SSH into your container

{% hint style="info" %}
**Do not** use SSH to install software required for production. Servers should be able to go down at any time and be started at any time wi th no human intervention. If you need custom software installation, please refer to [this guide](https://docs2.mobingi.com/v/v2/guides-and-tutorials/others/ssh-into-your-container).  
SSH is provided in the rare case you need to go on an actual production container to debug and check when something cannot be reproduced or has gone horribly wrong.
{% endhint %}

## Creating a keypair

First of all you should have a key pair specific to you on your computer. In order to check if you have one, simply type `ls ~/.ssh` in your console.

```bash
ore-no-pc:test david$ ls ~/.ssh/id_rsa		id_rsa.pub
```

