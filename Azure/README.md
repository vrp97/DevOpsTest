# Azure storage and static website


Here you will find the instruction for creating and configuring Azure storage from Azure CLI, at last you will get the generate link of static website hosted on Azure.


```bash
az login -u $username -p $password
az group create --name ExampleGroup --location "EastUS"
az deployment group create --resource-group ExampleGroup --template-file /fileDir/template.json
az storage blob service-properties update --account-name YourStorageAccName --static-website --404-document 404.html --index-document index.html
az storage blob upload-batch -s /dir/toWebpages/ -d '\$web' --account-name YourStorageAccName
az storage account show -n YourStorageAccName -g ExampleGroup --query 'primaryEndpoints.web' --output tsv
```
