# Azure Private Endpoint for Azure Monitor
Azure Monitor has a [different pattern](https://docs.microsoft.com/en-us/azure/azure-monitor/platform/private-link-security) for Private Endpoints than other Azure services. It uses a new resource type called a Private Link Scope to provide access to multiple Log Analytic Workspaces and Application Insight instances behind a single Private Endpoint. In addition to Private Link Scopes, it also needs to register DNS records in multiple private DNS zones.

This template provides an example of how to create all of these components and the private endpoint.

A sample parameters file is included in this repo.  An example of running this by specifying the parameters in az cli is below.

## Example
az deployment group create --resource-group=myrg --name=new --template-uri=https://raw.githubusercontent.com/mattfeltonma/arm-templates/master/examples/log-analytics-private-endpoint/deploy.json --parameters privateEndpointLocation=eastus privateEndpointVnetName=myvnet privateEndpointSubnetName=default laWorkspaceName=myworkspace laWorkspaceId=/subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourcegroups/myrg/providers/microsoft.operationalinsights/workspaces/myworkspace tags='{"tag1":"value","tag2":"value"}' --debug

