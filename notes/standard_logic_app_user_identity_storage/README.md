# Standard Logic App, User-Assigned Managed Identity, Blob Storage

It's a little tricky when connecting a standard logic app to a blob storage via user-assigned managed identity.

|                                                                                                  | Managed Blob Connector | Built-in Blob Connector |
|--------------------------------------------------------------------------------------------------|------------------------|-------------------------|
| User-Assigned Managed Identity                                                                   | Yes                    | No                      |
| Access Network Restricted Blob when the storage account and logic app are in the **same region** | No                     | Yes                     |


What if I want my standard logic app to access a network-restricted blob using a user-assigned managed identity?  

As the table shows, both managed and built-in blob connectors cannot satisfy these need.

Currently, the only way to achieve the above goal is by using the HTTP action, which supports both VNET and user-assigned identity, to directly call the Blob REST API. I use the [Get Blob endpoint](https://learn.microsoft.com/en-us/rest/api/storageservices/get-blob?tabs=microsoft-entra-id) as an example.
