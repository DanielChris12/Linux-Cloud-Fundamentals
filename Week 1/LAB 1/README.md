# Lab 1: Create a Linux virtual machine with the Azure CLI

The objective of the lab is to get you familiar with Azure CLI.
There are guides under this lab to help you navigate through the tasks. 
Happy Learning.


1. Launch Azure Cloud Shell
2. Create a resource group
3. Create virtual machine
4. Open port 80 for web traffic
5. Connect to virtual machine
6. Install web server
7. View the web server in action



Notes:
Quickstart: Create a Linux VM

https://docs.microsoft.com/en-us/azure/virtual-machines/linux/quick-create-cli

Quickstart for Bash in Azure Cloud Shell

https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart










## My Lab 1 Experience (steps)


## 1. Launch an Azure Cloud shell

Go to the Azure portal. Create an Azure account then you can access the Azure portal. When you at the portal interface go to the notification bars and click on the first box from your left. Clicking on that will launch the Azure Cloud shell.

## 2. Create a resource group

A Resource Group is a tool(a group that is saved on the portal) that holds every created resources for an Azure service. 
An azure resource group can be seen as a folder which is used to group related, interdependent or logically linked Azure resources together.

When creating an Azure Resource Group, you need to specify the following:

1. The region you want the Resource Group to be located.

2. The name of the Resource Group that is being created.

To create a simple resource group within a specified location I simply ran this command

_az group create --name MyResourceGroup1 --location eastus_

## 3. Create virtual machine

An Azure Virtual Machine can be created using either Azure Portal or the cloud shell or the Azure CLI. Using the Azure cloud shell, you can run the following steps to create a Virtual Machine.

az vm create
--resource-group myResourceGroup1
--name myVM
--image UbuntuLTS
--admin-username azureuser
--generate-ssh-keys



## 4. Open port 80 for web traffic

The virtual machine comes with various ports which allow different kinds of connections.

Port 80 is used for inbound traffic. This means that users on the internet can communicate with your compute instance via that port.

Port 22 is used for ssh connections. This is to give remote access to your virtual machine.

 To open port 80 for web traffic, all i need to do was run the command

_az vm open-port --port 80 --resource-group MyResourceGroup1 --name myVM_



## 5. Connect to virtual machine

 To connect to the VM or SSh into the VM as an administrator. I added a command (--generate-ssh-keys) this generates an authentication key that grants us secure connection into our VM. 
 
 Therefore,To ssh into the VM, all I need do is to run the ssh command like this,

ssh (adminusername)@public_ip_address


## 6. Install web server

The virtual machine does not automatically come with a server installed. To install a web server on the platform, i ran the command

_sudo apt-get -y install apacehe2_

This installs the latest version of apache server on your VM since the VM is to be used as a web server.

## 7. View Web Server In Action

To do this, I just need to go my VM and click the external IP address. It would redirect me to a URL which I would use to view my installed apache2 web page.
