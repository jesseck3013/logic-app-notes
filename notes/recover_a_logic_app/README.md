# Recover a Logic App

If you accidentally delete a logic app, don't panic. There are ways to get it back.

If you accidentally delete a Logic App and don't have any backup, can you recover it? The answer is yes, but there are time limitations.   
	- We can recover a consumption logic app within 90 days since it was deleted.
	- We can recover a standard logic app within 14 days since it was deleted
By default, we can only recover a consumption logic app within 90 days, and a standard logic app within 14 days of deletion.

## Consumption

A consumption logic app can be recovered from activity log.

## Standard

### The associated storage account exists 

Congratulations! That means everything is still there, you can simple deploy a new standard logic app and connect it to the original storage account.

### The associated storage account was deleted

Please follow this [document](https://learn.microsoft.com/en-us/azure/storage/common/storage-account-recover) to recover the associated storage account first. Then you can follow the previous step to recover your logic app.
