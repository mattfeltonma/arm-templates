# Azure Private Endpoint
This ARM template will create a private endpoint for a resource and output the private IP address of the private endpoint after creation.  The private DNS zone must exist prior to running this template.

## Example
az deployment group create --resource-group myrg --name=initial --template-file=deploy.json --parameters privateEndpointLocation=eastus privateEndpointVnetName=myvnet privateEndpointSubnetName=default resourceName=mystorageaccount resourceIdentifier=/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myrg/providers/Microsoft.Storage/storageAccounts/mystorageaccount privateDnsZoneName=privatelink.blob.core.windows.net privateEndpointSubResource='("blob",)' tags='{"some":"tag"}' --debug
