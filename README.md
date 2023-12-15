# Ansible Playbook for Creating Multipass VMs for a Cluster

This project contains an Ansible playbook that automates the process of creating Multipass VMs for a cluster.

## Playbook Tasks

The playbook performs the following tasks:

1. **Read cluster node VM configuration from file**: This task reads the configuration of the cluster node VMs from a file named `nodes.yml`.

2. **Create keypair and cloud-init**: This task creates a keypair and cloud-init by including tasks from a file named `create-keys-and-cloudinit.yml`.

3. **Create the cluster VMs**: This task creates the cluster VMs by including tasks from a file named `delete-and-create-new-vm-tasks.yml`. It uses the `vmname` and `vmcreationparams` variables, which are derived from the `nodes` dictionary.

4. **Create inventory file**: This task creates an inventory file by including tasks from a file named `create-inventory.yml`.

## How to Run

To run this playbook, use the following command:

```bash
ansible-playbook main-playbook.yml
```

# Ansible Playbook for Deploying a Web Application

This project contains an Ansible playbook that automates the process of deploying a web application on multiple nodes.

## Playbook Tasks

The playbook performs the following tasks:

1. **Clone git repository**: This task clones the git repository `https://github.com/iAlan02/api-xample.git` to the destination directory `/home/vadmin/api-xample`.

2. **Install Docker**: This task installs Docker using snap.

3. **Build container image**: This task builds a Docker container image with the tag `mexico-api` in the directory `/home/vadmin/api-xample`.

4. **Run container**: This task runs the Docker container on port 3000.

## How to Run

To run this playbook, use the following command:

```bash
ansible-playbook playbook.yml -i inventory.yml
```