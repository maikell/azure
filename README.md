# Azure Ansible repository

In this repository you will find several scripts to provision quickly a development environment.
Provisioning quickly and destroying the development environment each time enforces me/you to 
write Ansible scripts whereby the environment will be setup completely from code. No manual shortcuts :-)

* Per directory you will find Ansible playbooks to setup a certain environment/service/cluster. 

# prerequisites
* This repository and the playbooks assume you have already an azure account, installed Ansible, Azure pip libraries and authenticated.
You can find a manual here: https://docs.microsoft.com/en-us/azure/virtual-machines/linux/ansible-install-configure how
to setup the prerequisites for Ansible.
* You will also need to install Azure Cli packages and authenticate. The manual for doing this
can be found here: https://docs.microsoft.com/en-us/cli/azure/install-azure-cli-yum?view=azure-cli-latest. 

## vm_provison
This directory consists of three playbooks and one var file:
 * create_resouce_and_network.yml   
   Setup complete development environment, including NSG, public ip and NIC
 * create_vm.yml 
   Create a vm in the development resource. A public ip will be attached and check if SSH is available after provisioning.
 * destroy_all.yml
   Destroy the complete development resource. **BE AWARE** if you have any resource id called 'development', it will destroy this.
 * vars/main.yml
   Contains all the var files for provisioning. For most deployments it is the only file need to be edited. 

You will need to edit/tune vars/main.nl to make it work. Out of the box, the **only thing** you will need to do is add your ssh publickey and change the username.




