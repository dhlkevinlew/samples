# Azure Update Management

This sample deploys an Azure Automation account with the Azure Updates management solution and optional virtual machines, all auto-onboarded into the update solution. 

Azure Automation Update Management relies on linked automation and Log Analytics workspace, which has some regional requirements. For more information, see [Supported regions for linked Log Analytics workspace](https://docs.microsoft.com/azure/automation/how-to/region-mappings).

The `WestUS2` and `SoutheastAsia` regions are good options for this sample.

## Deploy sample

Create a resource group for the deployment.

```azurecli
az group create --name update-management --location SoutheastAsia
```

Run the following command to initiate the deployment.

```azurecli
az deployment group create \
    --resource-group update-management \
    --template-uri https://raw.githubusercontent.com/mspnp/samples/master/OperationalExcellence/azure-automation-update-management/azuredeploy.json \
    --parameters adminUserName=azureadmin adminPassword=Password2020! windowsVMCount=1 linuxVMCount=1
```

## Code of conduct

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/). For more information, see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.