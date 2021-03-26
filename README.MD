Provisioning an AWS EC2 Instance using "Terraform"
=================================================

At first create a directory called "terrfaorm" and then we should have the below three files in it.

first-ec2.tf ,  providers.tf  , variables.tf

first-ec2.tf  --> contains the below resource blocks in the terraform file 

1. Create a VPC as "tf-vpc" with CIDR range 10.0.0.0/16
2. Create a subnet as "subnet-tf" for the VPC 
3. Craete a internet gateway as "tf-gw" and attach it to the vpc 
4. Craete a route table as "route-table-tf" and attach it to the vpc
5. Associate the subnet with route table
6. Create a security group as "tf-sg" to allow SSH 
7. Create EC2 instance 
8. Create and attach the Elastic IP to the EC2 Instance 

providers.tf  --> contains the provider details ( in our case i have used 'AWS')

variables.tf --> Contains the variables as ( ami , aws key-name , instance-name), values can be passed at the time execution 

ami --> ami-0533f2ba8a1995cf9

key -->  your aws key name

instance-name --> first-tf-ec2

Note:
=====

1. Before executing first-ec2.tf file , you have to use "terraform init" to install the required plugins for the providers 
2. you must have authenticated your terraform machine to aws , either by configuring the aws access ,secret access keys or assigning the ec2 admin role to the machine.
3. when you enter terraform plan and terraform apply (it will prompt for the variable values that must be specified) 

Inorder to execute terraform script follow the below commands 

terraform init                           

terraform plan

terraform apply 





