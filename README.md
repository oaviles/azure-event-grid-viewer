Description: "Source code for a site that displays events from Azure Event Grid in near-real time."

# Azure Event Grid Viewer

This repository contains the source code for a site that displays events from Azure Event Grid in near-real time. It is built on ASP.NET Core 3.1 and leverages SignalR to display incoming messages.

For details about how it was put together, please refer to the [accompanying blog post](https://madeofstrings.com/2018/03/14/azure-event-grid-viewer-with-asp-net-core-and-signalr/).

## Deploy the solution

### 1. Deploy to Azure

This will launch a custom template for the Azure portal instance that you are logged into.

Run GitHub Action called "Deploy App Service and WebApp (ARM)", the workflow file reference is "deploy-webapps-dotnet-core.yml". Update paramenters in the file ["parameters-appservice.json"](https://github.com/oaviles/azure-event-grid-viewer/blob/main/IaC/parameters-appservice.json)

This will take about 3-5 minutes to provision.

### 2. Launch the site

Launch the site to ensure that it is running. Make note of the address for the next step.

### 3. Register the endpoint as an event subscription

The event subscription endpoint will be the address with the following suffix: */api/updates*.

For example: `https://{{site-name}}.azurewebsites.net/api/updates`

### 4. References

- [Routing events to a custom endpoint](https://docs.microsoft.com/azure/storage/blobs/storage-blob-event-quickstart?toc=%2fazure%2fevent-grid%2ftoc.json)
- [Receive events to an HTTP endpoint](https://docs.microsoft.com/en-us/azure/event-grid/receive-events)
