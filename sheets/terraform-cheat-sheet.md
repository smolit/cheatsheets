#####Destroy Specific Resources

terraform plan -destroy -target="module.<submodule>.<resourcetype>.<resourcename>"

terraform destroy -target="module.<submodule>.<resourcetype>.<resourcename>"

##### Import State of Resources

terraform import aws_iam_role.role_name my_role


#####Forcing Re-creation of Resources

  terraform apply -replace="aws_instance.example"
  
# Links

https://www.hashicorp.com/blog/terraform-azurerm-provider-4-0-adds-provider-defined-functions
  
https://medium.com/azure-terraformer/terraform-input-templating-with-the-templatestring-function-a81583777ed1 
