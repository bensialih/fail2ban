# fail2ban

## About

this repo looks at a setup of fail2ban on an ec2 amazon linux 2023 server

## Steps
- launch desired servers

## Ansible requirements
- required: `inventory.ini`

```
[pitcher]
ip_here

[catcher]
ip_here

[hosts:children]
pitcher
catcher


[pitcher:vars]
ansible_ssh_private_key_file=~/.ssh/location_of_ssh_key
ansible_ssh_user=ec2-user
ansible_host_key_checking=False

[catcher:vars]
ansible_ssh_private_key_file=~/.ssh/location_of_ssh_key
ansible_ssh_user=ec2-user
ansible_host_key_checking=False


[hosts:vars]
ansible_ssh_private_key_file=~/.ssh/location_of_ssh_key
ansible_ssh_user=ec2-user
ansible_host_key_checking=False


```


## running Ansible

check servers are reachable
- `ansible hosts -m ping -i ./inventory.ini`

run ansible playbook
- `ansible-playbook ./main.yml  -i ./inventory.ini`
