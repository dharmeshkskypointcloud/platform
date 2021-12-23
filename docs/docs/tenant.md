# Tenant Details

This section covers the basic details of the current tenant.
1. Tenant Name : Name of the tenant.
2. Business Name : Business name for the tenant.
3. Tenant Website URL : The official website URL of the tenant.
4. Tenant Identifier : When a tenant account gets registered on our platform, a unique id is alloted to that tenant for mapping and other reference purposes in our database. It cannot be changed once assigned.

## Resources

As soon as the tenant gets registered on our platform, a storage account gets created and assigned to that tenant for data storage and other purposes. With the Azure Data Lake Gen 2 offered to the tenant, Azure Cognitive Search service is also provided to the tenant by default. The credentials for the storage account and cognitive search are shared with the tenant. 
Also, the tenant has been given the ability to enter the credentials for a different storage account as there can be cases where the tenant has a working storage account set up to fulfill the demands. At first, the user has to create an app and give it proper access to the storage account in order to use other services offered by Azure.

![Alt text](https://github.com/skypointcloud/platform/blob/master/docs/doc_snippets/TenantDetails.PNG?raw=true)
