# Create multiple resources

This ARM template demonstrates how to create multiple instances of a resource using the [copy function](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/copy-variables).  While there are many [examples](https://docs.microsoft.com/en-us/azure/azure-resource-manager/templates/template-tutorial-create-multiple-instances?tabs=azure-cli) most of them demonstrate generation of a random name.  This example iterates across a variable with an array of unique strings.  The result is the creation of multiple [Application Security Groups](https://docs.microsoft.com/en-us/azure/virtual-network/application-security-groups) each with a unique name drawn from the array of strings.

