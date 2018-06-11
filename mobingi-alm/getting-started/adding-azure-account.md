# Adding Azure account

Microsoft Azure requires the security identity below to allow access to specific Azure resources.

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



