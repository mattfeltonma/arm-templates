# Azure Private DNS Link to Virtual Network
This creates a link from an existing Azure Private DNS Zone to an existing Virtual Network.  The link allows the Virtual Network to resolve records within the DNS namespace configured for the Azure Private DNS Zone.  The template can be used in scenarios where the Private DNS Zone and Virtual Network exist in the same tenant or when the Virtaul Network exists in a different tenant.

If you are linking a Virtual Network and Azure Private DNS Zone that exist in a separate tenant there are a few things you must be aware of:
* You must run the deployment from the context of the tenant where the Azure Private DNS Zone exists
* You will need sufficient permissions in both tenants to create the link
* You must use the [az cli](https://docs.microsoft.com/en-us/cli/azure/?view=azure-cli-latest) to perform the deployment.  The Azure PowerShell modules do not support obtaining an access token from the secondary tenant.

## Example Deployment
az deployment group create -g my_resource_group --template-file "C:\ARM\deploy.json" --parameters @"C:\ARM\parameters.json" --aux-tenant "55555555-5555-5555-5555-555555555555"