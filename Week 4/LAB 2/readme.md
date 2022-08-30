## Launch an Amazon linux instance using AWS CLI

Tasks:

Launch an instance with the following property 
1. instance OS   - Amzon linux
2. instance type - t2.micro
3. Region: Oregon
4. Network: Lab VPC, Public Subnet
5. Tag:  Key: Name     Value: ProdCafeServer
6. Security Group:  Create a  one named serverSG, with TCP port 22 and port 80 open to anywhere



Hint: Associate an elastic ip with this instance, you will need it in later lab.


Grading tip:  Screenshot major cli output and upload with your step by step answer (AWS describe command can help)


Guide:

https://docs.aws.amazon.com/cli/latest/userguide/cli-services-ec2-instances.html





## My LAB Experience 


## 1. Instance OS - Amazon Linux

The Amazon Linux AMI is a supported and maintained Linux image provided by Amazon Web Services for use on Amazon Elastic Compute Cloud (Amazon EC2). It is designed to provide a stable, secure, and high performance execution environment for applications running on Amazon EC2. It supports the latest EC2 instance type features and includes packages that enable easy integration with AWS. Amazon Web Services provides ongoing security and maintenance updates to all instances running the Amazon Linux AMI. The Amazon Linux AMI is provided at no additional charge to Amazon EC2 users.


  ## 2. Region(Oregon)

  Amazon cloud computing resources are hosted in multiple locations world-wide. These locations are composed of AWS Regions, Availability Zones, and Local Zones. Each AWS Region is a separate geographic area. Each AWS Region has multiple, isolated locations known as Availability Zones.

  Each AWS Region is designed to be isolated from the other AWS Regions. This design achieves the greatest possible fault tolerance and stability.
  
  When you view your resources, you see only the resources that are tied to the AWS Region that you specified. This is because AWS Regions are isolated from each other, and we don't automatically replicate resources across AWS Regions.

  As specified in this Lab my region was oregon, which means this instance would not be run on any other region apart from Oregon.

  ## 3. Network: Lab VPC, Public Subnet

  **Virtual private clouds (VPC)**
A VPC is a virtual network that closely resembles a traditional network that you'd operate in your own data center.

**Subnets**
A subnet is a range of IP addresses in your VPC. A subnet must reside in a single Availability Zone. 

  ## 4. Tag: Key: Name Value: ProdCafeServer

  A tag is a label that you assign to an AWS resource. Each tag consists of a key and an optional value, both of which you define.

  Tags enable you to categorize your AWS resources in different ways, for example, by purpose, owner, or environment.


## 4. Security Group: Create a one named serverSG, with TCP port 22 and port 80 open to anywhere.

A security group controls the traffic that is allowed to reach and leave the resources that it is associated with. For example, after you associate a security group with an EC2 instance, it controls the inbound and outbound traffic for the instance.

Therefore i ran this command to create one as specified 

_aws ec2 create-security-group --group-name serverSG--description "My security group"_


after i generated image-id, instance-type, key-name, security-id, subnet-id and tags by running the command i ran this command to launch my instance

_aws ec2 run-instances  --image-id ami-07d59d159373b8030 --count 1  --instance-type t2.micro  --key-name learningkey --security-group-ids sg-044174cdba0532d9c --subnet-id subnet-078cfe317c0bdf44b --tag-specifications 'ResourceType=instance,Tags=[{Key=learningkey,Value=prodCafeServer}]'_


## Here are the Screenshot

![lb2-a](https://user-images.githubusercontent.com/105374941/187482926-6d20c5c5-3938-4be6-9775-6ec57d3c15e0.png)

![lb2-b](https://user-images.githubusercontent.com/105374941/187482966-582aa5ea-ede5-416a-b044-49f3566bc649.png)

![lb2-z](https://user-images.githubusercontent.com/105374941/187483075-fe3c6684-1bac-4c7d-909e-b1442eeca6c5.png)

![lb2-d](https://user-images.githubusercontent.com/105374941/187483131-cd3b9e3e-99ec-4b14-89fb-afcdc7c3f663.png)

![lb2-e](https://user-images.githubusercontent.com/105374941/187483207-692b8513-8c4c-4014-bd36-568a6f2ce19a.png)


