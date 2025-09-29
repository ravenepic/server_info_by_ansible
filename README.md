# Server Info with Ansible
This playbook contains
* which ports are open in the system
* what all services are running in the system
* what all users are there in the system
* any mounted device in the system on /mnt
* which all services are enabled in the system
* info on OS patching, security patching, cron etc 


## Setup Instructions

```bash
sudo apt update && sudo apt install ansible-core -y
``` 
#create a file named hosts file, add the below cmds to the hosts file
```ini
[vm]
4.247.136.58   # your worker node IP address

[vm:vars]
ansible_ssh_private_key_file=~/devops.pem   # your private key
ansible_user=azureuser
# If the SSH port of worker node is changed from 22 to any other number, add this below line in the hosts file
#ansible_port=<your_port_no>
```

```bash
cd server_info_by_ansible/
```
```bash
ansible-playbook -i <path-to-your-hosts-file> <playbook-file-name>
```

