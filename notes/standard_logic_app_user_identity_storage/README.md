# Standard Logic App, User-Assigned Managed Identity, Blob Storage

It's a little tricky when connecting a standard logic app to a blob storage via user-assigned managed identity.

|                                                                                              | Managed Blob Connector | Built-in Blob Connector |
|----------------------------------------------------------------------------------------------|------------------------|-------------------------|
| User-Assigned Managed Identity                                                               | Yes                    | No                      |
| Access Network Restricted Blob when the storage account and logic app are in the same region | No                     | Yes                     |

