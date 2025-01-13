# Logic App Pricing

This note is not meant to replace the [formal documentation](https://learn.microsoft.com/en-us/azure/logic-apps/logic-apps-pricing). The formal document includes all the pricing details, but it is complex and hard to follow. I extract the most important part to help you understand the pricing model. Once you finish reading this note, you can refer to the formal documentation for more details.

# Plans

Normally, you'll either use a consumption plan or a standard plan. Their pricing models are completely different.

## Consumption Plan

There are three types of cost from a consumption plan:  
	- the number of actions that a logic app actually runs
	- the number of Api connection calls
	- storage

Please note that the price varies from different regions.

### Actions

- $0.000025 per Execution in West US.

Every time your logic apps run a built-in action, it generates a cost. 

The screenshot is a simple http server which includes two built-in actions. Every time this workflow runs, two built-in actions are metered.

You can check the connector type on the about page of an action.

![action](./action.png)

### Api connection calls 

- $0.000125 per Execution in West US.

Every time your Logic Apps run an action that belongs to a managed connector, the Logic App calls the underlying API connection, which generates a cost.

You can check the connector type on the about page of an action.

![connection](./connection.png)

### Storage

- $0.12 GB/month in West US.

Your logic apps need storage to store its run history. This storage generates a cost.

## Standard Plan

Buil-in actions are free to use. In addition, there are three types of cost from a consumption plan:  
	- the app service plan
	- the number of Api connection calls
	- storage

### App Service Plan

ASP charges by an hourly rate which differs from the allocated vcpu and memory. Once you deploy an app service plan, it starts generating cost until you delete the resource. Please note that ASP has an auto scale out feature, when there are too many requests, it adds more instances to serve those requests. 

The screenshot below is the monthly rate of three pricing tiers for standard logic app. The estimation is for one instance.

![asp](./asp.png)

### Api connection calls 

Same as consumption.

### Storage

A standard logic app uses a storage account to store its run history. It follows the storage account's pricing.
