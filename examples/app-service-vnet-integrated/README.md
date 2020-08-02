# Virtual Network-Integrated App Service with Forced Tunneling
This ARM template can be used to deploy an Azure App Service that is [VNet-integrated](https://docs.microsoft.com/en-us/azure/app-service/web-sites-integrate-with-vnet) and supports the [forced tunneling functionality](https://azure.github.io/AppService/2020/02/27/General-Availability-of-VNet-Integration-with-Windows-Web-Apps.html). 

Note that if you deploy this into a subnet with an existing route table applied, the route table will be removed.  Ensure you add a route table to the subnet after the template is deployed.

A sample parameters file has been provided.