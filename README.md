# Nutanix Datadog integration

This example shows how to integrate Datadog Virtual Machines, using infrastructure as code with [Terraform](https://www.terraform.io/) and the [Nutanix Provider for Terraform](https://registry.terraform.io/providers/nutanix/nutanix/latest). 


# Prerequisites

We'll need a working Nutanix cluster, and Terraform with the Nutanix provider for Terraform installed. 

## Required data

We need to know the following data about our environment:

 - Password for admin user
 - IP Address of your Prism Central and Prism Element 

# Using Terraform to deploy a new VM.

You can clone this repository with an easy eaxmple.

## Terraform files

Inside this repository you'll find the following 4 files:

|File|Description  |
|--|--|
|[main.tf](https://github.com/rafabolivar/terraform_nutanix_cloud-init/blob/main/main.tf)  | The main configuration file for our deployment |
|[variables.tf](https://github.com/rafabolivar/terraform_nutanix_cloud-init/blob/main/variables.tf)|The variable definition file|
|[terraform.tfvars](https://github.com/rafabolivar/terraform_nutanix_cloud-init/blob/main/terraform.tfvars)  | The variable values that will be used in our deployment |
|[init.tpl](https://github.com/rafabolivar/terraform_nutanix_cloud-init/blob/main/init.tpl)  | The cloud-init script that will configure our VM during the first boot |

This variables values must be modified, using the appropiate values from our cluster. You can do that using Nutanix Rest API or connecting via SSH to one of your CVMs and executing the following commands:

***Cluster UUID***

    ncli cluster get-params | grep "Cluster Uuid"
