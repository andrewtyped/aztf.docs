# aztf.docs
Documentation for an enterprise-y Terraform setup for Azure management

# Project Goals

Learn about well-organized infrastructure-as-code by doing. Build my own system for managing Azure resources that would scale for a mid-large enterprise.

# Project Components

## aztf.bootstrapper

https://github.com/andrewtyped/aztf.bootstrapper

Contains PowerShell for provisioning:

- a new resource group 
- a storage account with container for tfstate
- a service principal with federated credential for accessing the tfstate

This resource group will be responsible for hosting tfstate that tracks all resource groups in the subscription

## aztf.subscriptionRoot

https://github.com/andrewtyped/aztf.subscriptionRoot

Contains terraform for provisioning other resource groups in the subscription. Each resource group will be provisioned with:

- A storage account and container for tfstate
- a service principal with federated credential for accessing the tfstate.
- An Azure DevOps service connection for using the service principal at deploy time.