# Providers 

A provider in Terraform is a plugin that enables interaction with an API. 
This includes cloud providers, SaaS providers, and other APIs. The providers are specified in the Terraform configuration code. 


Here is an example of how to use the aws provider:

```hcl
provider "aws" {
  region = "us-west-1"
}

resource "aws_instance" "one" {
  ami = "ami-0123456789abceed1" # Change the AMI 
  instance_type = "t2.nano"
}
```

When Terraform runs, it will first install the aws provider. Then, it will use the aws provider to create the virtual machine.


There are many other providers available, and new ones are being added all the time.

Providers are an essential part of Terraform. They allow Terraform to interact with a wide variety of cloud providers and other APIs. This makes Terraform a very versatile tool that can be used to manage a wide variety of infrastructure.


## Different ways to configure providers in terraform

There are three main ways to configure providers in Terraform:

### In the root module 

This is the most common way to configure providers.
```hcl
provider "aws" {
  region = "us-west-1"
}

resource "aws_instance" "one" {
  ami = "ami-0123456789abcghj0"
  instance_type = "t2.micro"
}
```

### In a child module

This is useful if you want to reuse the same provider configuration in multiple resources.

```hcl
module "aws_vpc" {
  source = "./aws_vpc"
  providers = {
    aws = aws.us-west-2
  }
}

resource "aws_instance" "one" {
  ami = "ami-0123456789fghcdef0"
  instance_type = "t2.nano"
  depends_on = [module.aws_vpc]
}
```

### In the required_providers block

This is useful if you want to make sure that a specific provider version is used.

```hcl
terraform {
  required_providers {
    aws = {
      source = "hashicorp/aws"
      version = "~> 3.79"
    }
  }
}

resource "aws_instance" "one" {
  ami = "ami-0123456789asdfgef0"
  instance_type = "t2.large"
}
```

