# Deploy a Standard Logic App with Private Storage Account

[![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fjesseck3013%2Flogic-app-notes%2Frefs%2Fheads%2Ftemplates1%2Ftemplates%2Flogic_app_with_private_storage%2Ftemplate.json)

This template is a modified version of
https://github.com/VeeraMS/LogicApp-deployment-with-Secure-Storage, with the
following changes:

- update `FUNCTIONS_EXTENSION_VERSION` from `~3` to `~4`
- set `minimumTlsVersion` to `TLS1_2`
- set `publicNetworkAccess` to `Disabled`
- remove application insight resource
