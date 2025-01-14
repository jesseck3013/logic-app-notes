# Standard Logic App, User-Assigned Managed Identity, Blob Storage

It's a little tricky when connecting a standard logic app to a blob storage via user-assigned managed identity.

|                                                                                                  | Managed Blob Connector | Built-in Blob Connector |
|--------------------------------------------------------------------------------------------------|------------------------|-------------------------|
| User-Assigned Managed Identity                                                                   | Yes                    | No                      |
| Access Network Restricted Blob when the storage account and logic app are in the **same region** | No                     | Yes                     |


What if I want my standard logic app to access a network-restricted blob using a user-assigned managed identity? As the table shows, neither managed nor built-in blob connectors satisfy these need. Currently, the only way to achieve the above goal is by using the HTTP action, which supports both VNET and user-assigned identity, to directly call the Blob REST API. 

I use the [Get Blob endpoint](https://learn.microsoft.com/en-us/rest/api/storageservices/get-blob?tabs=microsoft-entra-id) as an example to demonstrate the configuration.

1. I whitelisted the VNET jcstd-vnet in the storage account's networking page.

![image](https://github.com/user-attachments/assets/a83ce435-fb5e-41d9-853b-9e8d2e92b704)


2. I added the VNET jcstd-vnet for my standard logic app's Outbound traffic configuration. I also checked the Outbound Internet traffic to ensure application traffic will go through the VNET.

![image](https://github.com/user-attachments/assets/d5b56ed5-ec05-4dc5-be7a-0809e889ff50)



3. I assigned the identity with Storage Blob Data Reader for the Get Blob endpoint.

![image](https://github.com/user-attachments/assets/9a65c0ff-54a8-415d-819e-e685aaaeae97)

4. I assigned the identity with **Storage Blob Data Reader** for the Get Blob endpoint.

5. Workflow

URI: https://myaccount.blob.core.windows.net/mycontainer/myblob  
Headers: x-ms-version  2017-11-09  
Authentication: user-assigned identity   
Audience: https://storage.azure.com/  

![image](https://github.com/user-attachments/assets/323b5bbf-49eb-4f82-9e40-178d46f75af6)

In the output of a testing run, we can see that the request succeeded with userAssignedIdentities.

![image](https://github.com/user-attachments/assets/894ed0e3-60c8-4ce9-9417-aadd262c16ce)
