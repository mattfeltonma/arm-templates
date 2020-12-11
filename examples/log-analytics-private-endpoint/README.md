# Azure Private Endpoint for Azure Monitor
Azure Monitor has a [different pattern](https://docs.microsoft.com/en-us/azure/azure-monitor/platform/private-link-security) for Private Endpoints than other Azure services. It uses a new resource type called a Private Link Scope to provide access to multiple Log Analytic Workspaces and Application Insight instances. In addition to Private Link Scopes, it also needs to register an DNS record in multiple private DNS zones.

This template provides an example of how to create all of these components and the private endpoint.  

## Example
az deployment group create --resource-group myrg --name=initial --template-file=deploy.json --parameters privateEndpointLocation=eastus privateEndpointVnetName=myvnet privateEndpointSubnetName=default resourceName=mystorageaccount resourceIdentifier=/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myrg/providers/Microsoft.Storage/storageAccounts/mystorageaccount privateDnsZoneName=privatelink.blob.core.windows.net privateEndpointSubResource='("blob",)' tags='{"some":"tag"}' --debug
