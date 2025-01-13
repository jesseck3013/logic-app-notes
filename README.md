# Logic App Notes

This repository is a collection of notes, templates, and scripts that I wrote for Azure Logic App.

## Templates

### [Standard Logic App with a Private Storage Account](/templates/logic_app_with_private_storage)

Deploy a standard logic app with a storage accont that is not publicly accessiable.

### [Secretless Standard Logic App](/templates/secretless_standard_logic_app)

Deploy a standard logic app that uses `managed identity` to access its associated storage account.

## Notes

### [Find Logic Apps by Api Connection](/notes/find_logic_app_by_api_connection)

Given an Api connection's resource id, find which all the logic apps that have reference to it.

### [Logic App Pricing](/notes/logic_app_pricing)

Understand the cost of using a logic app.
