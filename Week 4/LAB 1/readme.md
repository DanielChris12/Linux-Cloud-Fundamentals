# LAB: Working with Amazon CLI

## Task:

Create a VPC with the following property using the CLI:

1.  Name: LabVPC
2.  CIDR block 10.0.0.0/16
3.  Two subnets (one private with 10.0.1.0/24 and one public  10.0.0.0/24)
4.   Attach an internet gateway


Grading tip:  Screenshot each step and upload with your step by step answer


Guide:
https://docs.aws.amazon.com/vpc/latest/userguide/vpc-subnets-commands-example.html





## My LAB 1 Experience

## 1. Name: LabVPC


I created the VPC but i couldn't name it "LabVPC" but i got the VPC-ID after using the command below


_aws ec2 create-vpc --cidr-block 10.0.0.0/16 --query Vpc.VpcId --output text_


_Vpc-ID- vpc-0e870cbd22377ea37_

## 2. CIDR block 10.0.0.0/6

CIDR blocks are groups of addresses that share the same prefix and contain the same number of bits. The size of CIDR blocks are determined by the length of the prefix. Meanwhile, combination of multiple CIDR blocks into a larger whole sharing a common network prefix, is what called supernetting..

while creating the VPC i ensured my CIDR block was 10.0.0.0/6


## 3. Two subnets (one private with 10.0.1.0/24 and one public 10.0.0.0/24)

Subnet (subnetwork) are segmented piece of a larger network. They partition IP network into multiple, smaller network segment.. 
After creating my vpc with the CIDR block(10.0.0.0/16) to get my VPC-ID i ran the code below to create my subnet as stated in the exercise


_aws ec2 create-subnet --vpc-id vpc-0e870cbd22377ea37 --cidr-block 10.0.1.0/24_


_aws ec2 create-subnet --vpc-id vpc-0e870cbd22377ea37 --cidr-block 10.0.0.0/24_


i discovered that you can have more than one subnets on the same availability zone

## 4. Attach an internet gateway

An internet gateway enables resources in public subnets(such an EC2 instances) to connect to the internet if the resource has a public IPv4 address or an IPv6 address..

i created an internet gateway by using the command line below

_aws ec2 create-internet-gateway --query InternetGateway.InternetGatewayId --output text_


After which the command returns the ID of the created internet gateway -  _igw-0ff764fcc67602996_


i attached the internet gateway to the vpc with the created ID using the command line below


_aws ec2 attach-internet-gateway --vpc-id vpc-0e870cbd22377ea37 --internet-gateway-id igw-0ff764fcc67602996_


## Here are the screenshots below


![labvpc1](https://user-images.githubusercontent.com/105374941/186181294-33b90be7-9a06-43ac-b693-83ae4e4c0c13.png)



![labvpc2](https://user-images.githubusercontent.com/105374941/186181334-f1cdf730-b5fa-425a-b3f8-199abbce9f99.png)
