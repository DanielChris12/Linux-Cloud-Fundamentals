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












**My LAB 2 Experience**


**1. Create resoucre group**


I am now acquitted to creating resource groups using both GUi and CLi, I created different resource group using CLi.



**2. Create Virtual machine**

I created a virtual machine and named it Lab1az



**3. Connect to Virtual Machine**

 i ssh into the vm using the ssh command

ssh azureuser@public_ip_address



**4. Understand VM images**


VM Image is an OS template used to create a VM The VM images is the configuration of what i want my VM to carry, it includes the ram, the c.p.u, the disk etc. The VM Images are in hundreds, there are lots of configurations to pick from depending on the work we want to carry out. We have Images from different publisher like SUSE,Redhat,windows, coreos. The images are much so we can pick from any of them depending on the task. to see a list if VM images available, run the command

_az vm image list_ --output table



**5. Understand VM sizes**


The VM sizes determines the amount of compute resource, the memory avaliable to the VM. When we talk about VM size, we talk about how much resources the VM will consume. One needs to pick the size that would be enough for the workload to be done. If the task ahead requires much space to work with then it is advisable to pick a large size. One can also create the particular size needed for the job and also go ahead to partition it running some commands. to view a list of VM sizes in a particular region, run the command

_az vm list-sizes_ --location eastus --output table



**6. VM power State**


The VM power state shows the current state of the virtual machine. Maybe or not it is running,stopped, starting, deallocating. we achieve that by running some command on the cloud shell starting with (_az vm grt-instance-view_)


**7. Management task**


The management tasks such as deleting, starting, stopping, a VM. can be achieved using this various command for it various task. examples are


_az vm delete_(to delete a VM)

_az vm deallocate_ (to deallocate the vm)

_az vm start_ (to start up a vm that was stopped)

_az group delete_ (to delete a resource group)




(DISCLAIMER:I CONSULTED DIFFERENT ARTICLES TO COME UP WITH THIS CONTENT THAT AIDED MY UNDERSTANDING OF THE LAB WORK)