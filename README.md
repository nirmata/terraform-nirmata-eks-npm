# A Terraform module for deploying N4K, Policy sets and registering EKS clusters in NPM

The terraform module deploys N4K, best practice policy set, and pod security policy set and registers the EKS cluster with NPM.

Prerequisites:- 

	1. Existing EKS Cluster should be available.
	2. AWS CLI should be configured with EKS Cluster Access.

Note:- Currently this module is supported to:-

        1. OS:- CentOS, MacOS
        2. Terraform Version:- v1.3.6

## Steps to deploy the terraform module:

```
Make the necessary changes or replace the respective values to the main.tf file
```

## Usage:

```
module "eks-npm" {
  source                   = "nirmata/eks-npm/nirmata"
  aws_eks_cluster_name     = "AWS EKS cluster name"
  nirmata_api_key          = "Nirmata API token"
  licenseKey               = "License key value"
  nirmata_cluster_name     = "Name of the cluster to be registered in NPM"
}
```

```
terraform init
```

```
terraform plan -target module.eks-npm.nirmata_cluster_registered.eks-registered
```

```
terraform apply -target module.eks-npm.nirmata_cluster_registered.eks-registered
```

```
terraform plan
```

```
terraform apply
```

You should see the EKS cluster registered in NPM and N4K deployed along with all the policy set.
