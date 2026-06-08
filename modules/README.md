# Lab Azure Basic
Create a basic infrastructure across 2 Azure sites using Terraform (requires git and terraform). 


**!! For laboratory use only !!**
* Visible admin password
* Azure credentials in terraform.tfvars
* My token RO public repos in dockerhub

**Description**: https://github.com/gitrcr/tfaz-basic/blob/main/description.md

## Requeriments

* Terraform: https://developer.hashicorp.com/terraform/install
* Git: https://git-scm.com/install/windows
* Cloud Credentials for labs. **This deployment is not compatible with free accounts.**

## Deploy

### 1. Clone repo
```bash
# Clone repo
git clone https://github.com/gitrcr/tfaz-basic.git
cd tfaz-basic

```
### 2. Credentials and variables
Extract Azure Contributor credentials in the Bash Cloud Shell console. 

You can use this script: https://github.com/gitrcr/bootstrap#tfaz-credentialssh
```bash
# Azure Cloud Shell (bash)
bash <(wget -qO - https://raw.githubusercontent.com/gitrcr/bootstrap/refs/heads/main/terraform/tfaz-credentials.sh)
```
* Copy block between "====" markers
* Paste it into terraform.tfvars.rename file for all environments.
* Rename the file to terraform.tfvars

## 3. Initialize, Apply, and Destroy
Execute in each environment and module, or use **init_subdirs.ps1**
```bash
terraform init
terraform fmt
```
Execute in each environment:
```bash
terraform validate
terraform plan -out main.tfplan
# Apply
terraform apply main.tfplan

# Delete created objects
# terraform destroy
```

## 4. Usage
Structure and files config

### environment
Only 2 sites (*site1* and *site2*), for more, you can duplicate env dir, rename, modify the variables and start.

* **locals.tf**: location, project, *env*, networking, naming   (*env* varible define project principal naming)
* **main.tf**: instances number, network config, image          (*main.tf* to add modules o modify variables)


### modules
Rehusable code, dont require modify.

* **linux**: linux vm config
* **network**: vnet and subnets.
* **resource_group**: RG and locations config.
* **security**: NSG and associations, public ip, gateway
* **windows**: windows vm config

**References:**
* spaincentral
* francecentral
* northeurope
* westeurope
* belgiumcentral
