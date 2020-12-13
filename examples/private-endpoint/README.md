# Azure Private Endpoint
This ARM template will create a private endpoint for a resource.  The Private DNS Zone must already exist prior to running the template.

This template will output the IP address of the Private Endpoint for use in automated processes such as adding a user defined route or creating a firewall rule.

A sample parameters file is included in this repo and example of running the command from az cli and specifying the parameters directly is included below.

## Example
az deployment group create --resource-group myrg --name=initial --template-file=deploy.json --parameters privateEndpointLocation=eastus privateEndpointVnetName=myvnet privateEndpointSubnetName=default resourceName=mystorageaccount resourceIdentifier=/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myrg/providers/Microsoft.Storage/storageAccounts/mystorageaccount privateDnsZoneName=privatelink.blob.core.windows.net privateEndpointSubResource="blob" tags='{"tag1":"value","tag2":"value"}' --debug
