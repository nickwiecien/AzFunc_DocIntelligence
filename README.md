# Document Intelligence - Processing Orchestration using Azure Functions

Repo contains an Azure Durable Functions project for extracting content from PDF documents loaded in an Azure Storage container using Azure Document Intelligence. Post-extraction all records are added to an Azure Cosmos DB collection.

## Deployment Steps

### Prerequisites
The following services should be deployed in your Azure environment:
- Azure Storage
- Azure Document Intelligence
- Azure Functions (Python Runtime; Version 3.11)
- Azure Cosmos DB
