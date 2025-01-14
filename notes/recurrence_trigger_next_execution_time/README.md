# Verifying the Next Execution Time for a Recurrence Trigger

Knowing the next execution time can help avoid misconfigurations. It's especially useful when the next run starts a few days later, as we don't want to wait that long to confirm if a trigger is working correctly. 

Azure REST API, Azure Powershell, Azure CLI can 

This notes demonstrate the script in powershell. You can do the same thing with Azure REST API, Azure CLI or other SDKs.

## Consumption

- Replace <subscription id>, <resource group name>, <workflow name> with the corresponding values.

```pwsh
Set-AzConText -Subscription "<subscription id>"
Get-AzLogicAppTrigger -ResourceGroupName "<resource group name>" -Name "<workflow name>"
```

The screenshot is the example output.  
![consumption](./consumption.png)
