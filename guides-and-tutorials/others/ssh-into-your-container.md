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

As above, if you do not see id\_rsa and id\_rsa.pub, then you need to create one by using the `ssh-keygen`command:

```bash
ore-no-pc:test david$ ssh-keygenGenerating public/private rsa key pair.Enter file in which to save the key (/Users/david/.ssh/id_rsa):Enter passphrase (empty for no passphrase):Enter same passphrase again:Your identification has been saved in meow.Your public key has been saved in meow.pub.The key fingerprint is:8d:b9:76:d5:24:b9:26:80:08:f0:e0:03:fc:1c:84:6e david@ore-no-pc.localThe key's randomart image is:+--[ RSA 2048]----+|=.+.             ||                 ||.o+ o            ||                 ||.                ||         . +     ||        o .      ||       . .       ||                 |+-----------------+
```

