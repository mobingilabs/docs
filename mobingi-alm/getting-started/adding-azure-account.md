# Adding Azure account

Microsoft Azure requires the credentials below to allow access to specific Azure resources.

1. Application ID
2. Secret Access key
3. Subscription ID
4. Directory ID

As a prerequisite, you must have sufficient permissions in both your Azure Active Directory and your Azure subscription. Specifically, you must be able to create an app in the Active Directory, and assign a role to the service principal.[\(Check Permission\)](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions)

## Using Azure portal to create necessary credentials

▪️[Create an Azure Active Directory application](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal#create-an-azure-active-directory-application)

▪️[Get Created Application ID and Add authentication key](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal#create-an-azure-active-directory-application)

▪️[Get Tenant ID\(Your tenant ID is your Directory ID\)](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal#get-tenant-id)

▪️[Assign application to role/subscription](https://docs.microsoft.com/en-us/azure/azure-resource-manager/resource-group-create-service-principal-portal#assign-application-to-role)

## Adding Azure credential to your ALM account

1. In the upper right of the page, click your `username` and then `General Settings`

![](../../.gitbook/assets/screen-shot-2018-06-11-at-17.10.20.png)

2. In the left side-menu, click `Setup Credentials` and select `Azure`

![](../../.gitbook/assets/screen-shot-2018-06-11-at-17.13.27.png)

3. Enter your preferred account name and the `Application ID`, `Secret Access Key`, `Subscription ID`, `Directory ID` you created in the _**Using Azure portal to create necessary credentials**_ section and click _**Add Account**_ button

![](../../.gitbook/assets/screen-shot-2018-06-11-at-17.16.53.png)

4. Your credential is added at the bottom of the page.

![](../../.gitbook/assets/screen-shot-2018-06-11-at-17.30.11.png)

