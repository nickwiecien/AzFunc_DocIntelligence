# Document Intelligence - Processing Orchestration using Azure Functions

Repo contains an Azure Durable Functions project for extracting content from PDF documents loaded in an Azure Storage container using Azure Document Intelligence. Post-extraction all records are added to an Azure Cosmos DB collection.

## Deployment Steps

### Prerequisites (Azure Services)
The following services should be deployed in your Azure environment:
- Azure Storage
- Azure Document Intelligence
- Azure Functions (Python Runtime; Version 3.11)
- Azure Cosmos DB

### Prerequisites (Local Installations)
- [Azure CLI](https://learn.microsoft.com/en-us/cli/azure/install-azure-cli-windows?tabs=azure-cli)
- [Azure Functions Core Tools](https://learn.microsoft.com/en-us/azure/azure-functions/functions-run-local?tabs=windows%2Cisolated-process%2Cnode-v4%2Cpython-v2%2Chttp-trigger%2Ccontainer-apps&pivots=programming-language-python)


### Configuration
Configure the environment variables in your Azure Function App settings as follows. You can also create `local.settings.json` file by copying the `sample.settings.json` file contained in this repo. Update the variables according to the table below.

| Variable Name                | Description                                               |
|------------------------------|-----------------------------------------------------------|
| `STORAGE_CONN_STR`           | Azure Storage account connection string                   |
| `DOC_INTEL_ENDPOINT`         | Endpoint for Azure Document Intelligence service          |
| `DOC_INTEL_KEY`              | Key for Azure Document Intelligence service               |
| `COSMOS_ENDPOINT`        | Endpoint for the Azure Cosmos DB instance              |
| `COSMOS_KEY`        | Key for the Azure Cosmos DB instance              |
| `COSMOS_DATABASE`        | Name of the Azure Cosmos DB database which will hold document extraction records              |
| `COSMOS_CONTAINER`        | Name of the Azure Cosmos DB collection which will hold document extraction records              |

### Deployment
Recommend deploying the functions using the commands below:
```
# Azure Functions Core Tools Deployment
func azure functionapp publish <YOUR-FUNCTION-APP-NAME>
func azure functionapp publish <YOUR-FUNCTION-APP-NAME> --publish-settings-only
```