# Deploy a Secretless Standard Logic App

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fjesseck3013%2Flogic-app-notes%2Frefs%2Fheads%2Ftemplates1%2Ftemplates%2Flogic_app_with_private_storage%2Ftemplate.json)

By default, standard logic app uses a connection string to access its associated storage account. For security consern, using secrets might not be a good practice. This [document](https://learn.microsoft.com/en-us/azure/logic-apps/create-single-tenant-workflows-azure-portal#set-up-managed-identity-access-to-your-storage-account) provides a way to use `managed identity` to connect your standard logic app to a storage account. I wrapped all the configurations in this template.

