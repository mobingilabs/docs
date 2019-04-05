---
description: >-
  You only define your architecture requirements, plus where application code is
  hosted, then Mobingi ALM automates the rest for you
---

# Preparation

* This page explains things you need to be done on your AWS account for start using Mobingi Ripple.
* After finishing preparation, you will need to give Mobingi the below informations. 

```text
- AWS account ID (12 digit numbers).

- Information of the report you made.

    - Report name

    - S3 bucket

    - Report path prefix, or Report path

- ARN of IAM Role which allow the specific bucket.(Ex: arn:aws:iam::xxxxxxxxxxxx:role/crossacounnt-access-for-mobingi)
```

## Step 1 : Create S3 bucket and daily report \(option\) <a id="step1"></a>

* Create daily repot with the AWS account you want to share the billing information with Ripple.
* You can skip if you already have the report definition with below conditions.

  `Time unit:` `Hourly`

  `Rsource IDsis included in the report.`

  `There is no object which Mobingi shouldn't see.(Since the access atuhority will be a whole bucket).`

### Step1-1: **Create S3 bucket**

* Create bucket with any name from S3 bucket. Option can leave as default.

  Please keep the bucket name for using it as output destination of report.

### Step1-2: Create daily report

* Choose **Billing** from AWS management console and move to **Reports**.

Click **Create report**.

![](../.gitbook/assets/snip20180727_7.png)

* Fill out `Step 1: Select Content` same as below.
  * Report name: Any
  * Time unit: **Hourly**
  * Include: **Resource IDs**
  * Enable support for...: Optional

![](../.gitbook/assets/snip20181004_14.png)

* `Step2: Select Delivery Options` will be the following process.
  * Put S3 bucket name \(you made at Step1-1\)
  * Display and copy **Sample policy** \(\* make sure to click after you entered S3 bucket name\)

![](../.gitbook/assets/snip20181004_16.png)

![](../.gitbook/assets/snip20180727_10.png)

* After copy **sample policy,** open the **S3 bucket which you create on step1-1** and open detail \(\* we suggest to open the page with new window or new tab\).
* On S3 page, go to **Permissions** &gt;&gt; **Bucket Policy.**
* Put the policy you copied at before into **Bucket policy editor** and Save.

![](../.gitbook/assets/snip20180727_17.png)

Go back to `Step2: Select Delivery Options` and put below info.

* Report path prefix: Optional  \(\*blank also works\) 
* Compression: Optional

It shows **Valid Bucket** only when the bucket policy is correct.

Check your S3 again.

![](../.gitbook/assets/snip20181004_16%20%281%29.png)

Check the info again and click **Review and Complete.**

![](../.gitbook/assets/snip20181004_18.png)

## Step 2 : Create IAM role for Mobingi <a id="step2"></a>

From AWS management console, select **IAM** service and click **Roles** &gt;&gt; **Create role.**

![](../.gitbook/assets/snip20180727_19.png)

Choose **Another AWS Account** at `Select type of trusted entity`and put Mobingi account ID.

* Mobingi Account ID: 131920598436

![](../.gitbook/assets/snip20180727_21.png)

Click **Create policy**.

![](../.gitbook/assets/snip20180727_23.png)

New tab or window will open. Choose JSON as input format and type the policy same as below. Make sure to change`{replace_to_report_bucket}` at "Resource" to **the bucket name you use for report.**

```bash
{
    "Version": "2012-10-17",
    "Statement": [
         {
               "Effect": "Allow",
               "Action": [
                     "s3:Get*",
                     "s3:List*"
               ],
               "Resource": [
                     "arn:aws:s3:::{replace_to_report_bucket}",
                     "arn:aws:s3:::{replace_to_report_bucket}/*"
               ]
         }
   ]
}
```

![](../.gitbook/assets/create-policy-en.png)

After fill the informations below, you can finish to create policy.

* Name: Any \(\*required\)
* Description: Option

![](../.gitbook/assets/snip20180727_31.png)

Go back to **Create Role** and refresh, the policy suppose to display on the list. Active the policy and move to review page. _\*\*_

![](../.gitbook/assets/snip20180727_33.png)

At **Review**, fill the informations below.

* Role name: Any \(\*required\)
* Role description: Option

After check **Trusted entities** and **Policies** are correctly applied, click **Create role**.

![](../.gitbook/assets/snip20180731_39.png)

Keep the ARN of the role.

