---
title: Azure DevCenter REST client library for JavaScript
keywords: Azure, javascript, SDK, API, @azure-rest/developer-devcenter, devcenter
ms.date: 07/08/2024
ms.topic: reference
ms.devlang: javascript
ms.service: devcenter
---
# Azure DevCenter REST client library for JavaScript - version 1.0.0 



The Azure DevCenter library provides access to manage resources for Microsoft Dev Box and Azure Deployment Environments. This package enables managing developer machines and environments in Azure.

Use the package for Azure DevCenter to:
> Create, access, manage, and delete Dev Box resources
> Create, deploy, manage, and delete Environment resources

DevCenter service

**Please rely heavily on our [REST client docs](https://github.com/Azure/azure-sdk-for-js/blob/@azure-rest/developer-devcenter_1.0.0/documentation/rest-clients.md) to use this library**

Key links:

- [Source code](https://github.com/Azure/azure-sdk-for-js/tree/@azure-rest/developer-devcenter_1.0.0/sdk/devcenter/developer-devcenter-rest)
- [Package (NPM)](https://www.npmjs.com/package/@azure-rest/developer-devcenter)
- [API reference documentation](/javascript/api/@azure-rest/developer-devcenter)
- [Samples](https://github.com/Azure/azure-sdk-for-js/tree/@azure-rest/developer-devcenter_1.0.0/sdk/devcenter/developer-devcenter-rest/samples)

## Getting started

### Currently supported environments

- LTS versions of Node.js

### Prerequisites

- You must have an [Azure subscription](https://azure.microsoft.com/free/) to use this package.
- You must have [configured](https://learn.microsoft.com/azure/dev-box/quickstart-configure-dev-box-service) a DevCenter, Project, Network Connection, Dev Box Definition, and Pool before you can create Dev Boxes 
- You must have [configured](https://learn.microsoft.com/azure/deployment-environments/) a DevCenter, Project, Catalog, and Environment Type before you can create Environments
 
### Install the `@azure-rest/developer-devcenter` package

Install the Azure DevCenter REST client REST client library for JavaScript with `npm`:

```bash
npm install @azure-rest/developer-devcenter
```

### Create and authenticate a `AzureDeveloperDevCenterClient`

To use an [Azure Active Directory (AAD) token credential](https://github.com/Azure/azure-sdk-for-js/blob/@azure-rest/developer-devcenter_1.0.0/sdk/identity/identity/samples/AzureIdentityExamples.md#authenticating-with-a-pre-fetched-access-token),
provide an instance of the desired credential type obtained from the
[@azure/identity](https://github.com/Azure/azure-sdk-for-js/tree/@azure-rest/developer-devcenter_1.0.0/sdk/identity/identity#credentials) library.

To authenticate with AAD, you must first `npm` install [`@azure/identity`](https://www.npmjs.com/package/@azure/identity) 

After setup, you can choose which type of [credential](https://github.com/Azure/azure-sdk-for-js/tree/@azure-rest/developer-devcenter_1.0.0/sdk/identity/identity#credentials) from `@azure/identity` to use.
As an example, [DefaultAzureCredential](https://github.com/Azure/azure-sdk-for-js/tree/@azure-rest/developer-devcenter_1.0.0/sdk/identity/identity#defaultazurecredential)
can be used to authenticate the client.

Set the value of dev center endpoint as environment variable:
DEVCENTER_ENDPOINT

## Key Concepts

### REST Client

This client is one of our REST clients. We highly recommend you read how to use a REST client [here](https://github.com/Azure/azure-sdk-for-js/blob/@azure-rest/developer-devcenter_1.0.0/documentation/rest-clients.md).

### DevCenter Concepts
Dev Boxes refer to managed developer machines running in Azure. Dev Boxes are provisioned in Pools, which define the network and image used for a Dev Box.

Environments refer to templated developer environments, which combine a template (Catalog Item) and parameters, as well as an Environment Type which defines permissions and where the resources are deployed.

## Troubleshooting

### Logging

Enabling logging may help uncover useful information about failures. In order to see a log of HTTP requests and responses, set the `AZURE_LOG_LEVEL` environment variable to `info`. Alternatively, logging can be enabled at runtime by calling `setLogLevel` in the `@azure/logger`:

```javascript
const { setLogLevel } = require("@azure/logger");

setLogLevel("info");
```

For more detailed instructions on how to enable logs, you can look at the [@azure/logger package docs](https://github.com/Azure/azure-sdk-for-js/tree/@azure-rest/developer-devcenter_1.0.0/sdk/core/logger).

