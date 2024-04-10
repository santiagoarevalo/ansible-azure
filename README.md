# ansible-azure

Ansible is an open source IT automation engine that automates provisioning, configuration management, application deployment, orchestration, and many other IT processes. It is free to use, and the project benefits from the experience and intelligence of its thousands of contributors.
This time, we'll take a closer look at some basic Ansible fundamentals by **deploying a Docker container on an Azure virtual machine**.

## Prerequisites
- Have a virtual machine in Azure, accessible from SSH. For this you can check the following repository: [az-virtual-machine-modular](https://github.com/santiagoarevalo/az-virtual-machine-modular)
- Have Ansible installed in the environment where the deployment is going to be performed (Codespace or local). If you do not have it installed, you can follow the [following documentation](https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html) for installation.

## Step by step for install Docker in VM

1. First, we create a folder to be called inventory. In this folder we will create a file called hosts.ini. This will contain the general configuration of ansible and the credentials.
2. Then, we will create the file ansible.cfg. This contains the access paths to roles and inventory.
3. After this, we create a directory called playbooks. In this, we will create two files of type yml, which declare us what is necessary for each one of the two actions. At this point we create the roles.
4. After having indicated the roles, they must be created. For this, we create a directory called "roles". In this directory, we will create another folder for each established role. And, within these folders, a folder called Tasks. We will create two main.yml in each task directory, these will contain the instructions or actions that must be executed to deploy the container in Docker.

## Commands

Listed below are the commands used and their purpose.

* ````ansible-playbook -i inventory/hosts.ini playbooks/install_docker.yml````: The command runs the Ansible playbook which is responsible for installing Docker on the hosts that are defined in the inventory file.
* ````chmod 775 .````: It grants full permissions to the owner of the workspace. This command comes in salvation of the previous one when the following error occurs:
  
  ![image](https://github.com/santiagoarevalo/ansible-azure/assets/71450411/90ebdb98-7b10-44d7-a0e7-62c66e383536)
