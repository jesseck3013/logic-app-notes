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

### [Verifying the Next Execution Time for Recurrence Trigger](/notes/recurrence_trigger_next_execution_time)

Knowing the next execution time can help avoid misconfigurations. It's especially useful when the next run starts a few days later, as we don't want to wait that long to confirm if a trigger is working correctly.

### [Standard Logic App, User-Assigned Managed Identity, Blob Storage](/notes/standard_logic_app_user_identity_storage)

Neither built-in nor managed connectors support accessing a network-restricted blob storage with a user-assigned identity. This note provides a workaround for this problem.
