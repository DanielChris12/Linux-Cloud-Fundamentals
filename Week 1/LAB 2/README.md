# Lab 2: Manage Linux VMs with the Azure CLI

Task: 

1. Create resource group
2. Create virtual machine
3. Connect to VM
4. Understand VM images
5. Understand VM sizes
6. VM power states
7. Management tasks


Notes:
Quickstart: Create a Linux VM

https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-vm
Quickstart for Bash in Azure Cloud Shell

https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart










## My LAB 2 EPERIENCE

## 1. Create resoucre group
I am now acquitted to creating resource groups using both GUi and CLi, I created different resource group using CLi.

## 2. Create Virtual machine
I created a virtual machine and named it myfirstVM

## 3. Connect to VM

i was able to connect after i read through an article on how to create a key pair using the ssh-keygen command. after this i was able to ssh into the vm using the ssh command

ssh azureuser@public_ip_address

## 4. Understand VM images

The VM images is the configuration of what i want my VM to carry, it includes the ram, the c.p.u, the disk etc. The VM Images are in hundreds, there are lots of configurations to pick from depending on the work we want to carry out. We have Images from different publisher like SUSE,Redhat,windows, coreos. The images are much so we can pick from any of them depending on the task. to see a list if VM images available, run the command

_az vm image list --output table_

## 5. Understand VM sizes

The VM sizes determines the amount of compute resource, the memory avaliable to the VM. When we talk about VM size, we talk about how much resources the VM will consume. One needs to pick the size that would be enough for the workload to be done. If the task ahead requires much space to work with then it is advisable to pick a large size. One can also create the particular size needed for the job and also go ahead to partition it running some commands. To view a list of VM sizes in a particular region, run the command

_az vm list-sizes --location eastus --output table_

## 6. VM power State

The VM power state shows the current state of the virtual machine. Maybe or not it is running,stopped, starting, deallocating. we can view the power state by running some command on the cloud shell starting with (az vm grt-instance-view) then add other subcommands. 
Example;

_az vm get-instance-view --name myVM --resource-group myResourceGroupVM --query instanceView.statuses[1] --output table_

## 7. Management task

One will want to manage the VM and will want to run the management tasks such as deleting, starting, stopping, a VM. Using various command for various task. examples are

_az vm delete(to delete a VM)_

_az vm deallocate (to deallocate the vm)_

_az vm start (to start up a vm that was stopped)_

_az group delete (to delete a resource group)_