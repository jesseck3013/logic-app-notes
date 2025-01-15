# Recover a Logic App

If you accidentally delete a logic app, don't panic. There are ways to get it back.

## Consumption

A consumption logic app can be recovered from activity log.

Please go to the logic app's subscription -> activity log

### 1. Filter operation name by Delete Workflow.  
   
   ![image](https://github.com/user-attachments/assets/6aa3af72-a075-4969-bee3-f9f2dd9e555a)

### 2. Find the delted logic app by resource id.

![image](https://github.com/user-attachments/assets/364ee246-a9aa-4466-af19-9aede92ad318)

### 3. Open the Change History page and click on `<deleted resource>`

![image](https://github.com/user-attachments/assets/7884193c-b493-4666-9b4b-4e2a36380498)

### 4. The JSON definition is in the old value section.

![image](https://github.com/user-attachments/assets/81e96b6e-d1db-40b6-81af-3ce798afd0ca)


## Standard

### The associated storage account exists 

Congratulations! That means everything is still there, you can simple deploy a new standard logic app and connect it to the original storage account.

#### 1. Find the original file share name

Go to the storage account's file share, copy the file share name of the standard logic app.

![image](https://github.com/user-attachments/assets/0e67c2be-59a8-4496-99e4-989e7feb0c7d)

#### 2. Deploy a new standard logic app with the original storage account.

You can select the existing storage account during deployment.

![image](https://github.com/user-attachments/assets/89d26b79-a291-4358-ae25-c6ec1478716b)

#### 3. After deployment, update the environment variable WEBSITE_CONTENTSHARE with the original file share's name

![image](https://github.com/user-attachments/assets/83fe1288-2e7a-4c31-802e-011e7b4e16d1)

### The associated storage account was deleted

Please follow this [document](https://learn.microsoft.com/en-us/azure/storage/common/storage-account-recover) to recover the associated storage account first. Then you can follow the previous step to recover your logic app.
