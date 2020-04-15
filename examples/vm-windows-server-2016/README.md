# Azure Virtual Machine - Windows Server 2016
This ARM template provisions a Windows Server 2016 Azure Virtual Machine.  It is configured with the following traits:
* Single virtual network interface set for a dynamic private IP address
* Storage account which is used for diagnostics logging
* Network Watcher extension installed
* Microsoft Monitoring Agent installed and configured for a Log Analytics Workspace

A sample parameter file is included which demonstrates how to provide parameters sourced from Azure Key Vault.
