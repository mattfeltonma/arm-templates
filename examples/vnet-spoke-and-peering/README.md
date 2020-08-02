# Azure Virtual Network - Spoke Virtual Network and Peering with Hub Virtual Network
This ARM template provisions a Virtual Network with the following properties:
* Two subnets one for the application and one for the data components
* Custom DNS servers configured for the spoke Virtual Network

It then peers the spoke Virtual Network to an existing hub Virtual Network.  It provides optional parameters if the hub Virtual Network exists in a different subscription or resource group.
