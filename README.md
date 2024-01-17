
## Usage
Please configure below environment variables as per your need on terraform.tfvars

```hcl
#Terraform variable values as per Environment
project_id      = "<PROJECT_ID>"
region          = "<REQUIRED_REGION>"
zone            = "<REQUIRED_ZONE>"
#Subnet for gke
ip_cidr_range   = "10.10.0.0/24"
machine_type    = "e2-medium"
#worker node size
disk_size_gb    = 20
# Autoscaling min & max worker nodes
min_node_count  = 2
max_node_count  = 3
#reguired gke_version
gke_version     = "1.26.2"

```

Then perform the following commands on the root folder:

- `terraform init` to get the plugins
- `terraform plan` to see the infrastructure plan
- `terraform apply` to apply the infrastructure build
- `terraform destroy` to destroy the built infrastructure

## Install

### Terraform
Be sure you have the correct Terraform version, you can choose the binary here:
- https://releases.hashicorp.com/terraform/

## File structure
The project has the following folders and files:

- /: root folder
- /main.tf: main file for this module, contains gcs bucket which should be created at first
- /variables.tf: all the variables for the module
- /vpc.tf: having gke network and required subnet
- /output.tf: the outputs of the module
- /terraform.tfvars: provide required variables values for peoject specific
- /README.md: this file
