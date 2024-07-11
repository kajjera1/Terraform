 # Terraform

 its a infrastructure automation tool.
 
 its platform independent


ADVANTGAES:
1. Reuseable 
2. Time saving
3. Automation
4. Avoiding mistakes


# Terraform installation 

##Pre-Requisites 
1) Install AWS CLI (Command Line Interface): https://aws.amazon.com/cli/
2) Cloud Platform Account (AWS, Azure, GCP, Openstack etc..)
3) IAM User account (Secret Key and Access Key)
4) IAM User should have resources Access
5) Configure AWS CLI Credentials:

       aws configure


1 . Create EC2 instance (amazon Linux)

2 . Connect to EC2 VM using Mobaxterm

3 . Swith to root user 
     $ sudo su -

4 . [go to terraform doc get command]
   
    $ sudo yum install -y yum-utils
   
    $ sudo yum-config-manager --add-repo https://rpm.releases.hashicorp.com/AmazonLinux/hashicorp.repo
   
    $ sudo yum -y install terraform

5 . Check Terraform Version
    
     $ terraform -v  
   
6 . aws configure
 
 give access key & secret key , give region, output formate    


# TERRAFORM COMMANDS:

  Initalize the provider plugins on backend
 
    $ terraform init	

 Format your script (indent spaces)
 
    $ terraform fmt 

 To create execution plan

    $ terraform plan	 

To create resources

    $ terrafrom apply 

To delete resources

    $ terrafrom destroy 
