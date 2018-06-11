# Deploy stack

## Create application stack \(AWS\)

Here, we explain our core feature "Lifecycle Management".   
Before you can start using Mobingi ALM for AWS to manage AWS resources on your behalf, you first need to provide your AWS credentials.

### Register AWS credentials

Open [dashbord,](https://console.mobingi.com/) then click**『Grant Permission』**

Type AWS **Access Key ID** and **Secret Access Key**.  
Don't know how to get an Access Key ID and Secret Access Key? Go to [here.](https://docs.mobingi.com/your-first-application/aws)  
Additionally, Mobingi ALM supports multi account system, so user can register multiple AWS accounts in the same Mobingi account.

![](../../.gitbook/assets/authoaws.png)

### Create application stack

Let's make your first application stack through mobingi ALM!

* Click**『Application Stacks』--&gt;『Create New Stack』**
* Choose AWS as cloud vendor.

![](../../.gitbook/assets/create_aws1.png)

* Choose Region.
* Select Instance type.
* You can define Number of Spot Instances by mouse dragging. By using spot instance, you can save 80% of EC2 cost maximum.
* Define Auto-Scale Range. Mobingi ALM software automatically creates ELB, Subnet, Networks, and other resources which are necessary.

![](../../.gitbook/assets/create_aws2.png)

* Choose Image Layer.
* By clicking 『Create Application』, the software will start creating your application stack.

![](../../.gitbook/assets/aws3.png)

