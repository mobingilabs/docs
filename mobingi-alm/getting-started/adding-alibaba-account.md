# Adding Alibaba account

ALM requires the credentials below to allow access to specific Alibaba Cloud resources.

* AccessKeyID
* AccessKeySecret

We recommend you to use RAM user as Alibaba Cloud credentials to ALM. To create a RAM user, please follow the steps below:

**Step 1**: Log into your Alibaba Cloud console and find "Resource Access Management \(RAM\)" section, create the policy.

The contents of the policy can be checked on ALM:

![](../../.gitbook/assets/ram-policy.png)

Copy the above the policy contents and create the policy on Alibaba Cloud console:

![](../../.gitbook/assets/create-ram-policy.png)

**Step 2**: Create the RAM user and attach the policy.

Create the RAM user:

![](../../.gitbook/assets/create-ram-user.png)

Attach the previously created policy to the RAM user:

![](../../.gitbook/assets/attach-ram-policy.png)



![](../../.gitbook/assets/ram-access-key.png)

