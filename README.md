# Server Info with Ansible

This project collects server information (OS details, patch info, updates) using Ansible.

## Setup Instructions

sudo apt update && sudo apt install ansible-core -y

```ini
[vm]
4.247.136.58   # your worker node IP address

[vm:vars]
ansible_ssh_private_key_file=~/devops.pem   # your private key
ansible_user=azureuser
# If the SSH port of worker node is changed from 22 to any other number, add:
ansible_port=<your_port_no>

cd server_info_by_ansible/


