# Ansible related examples

## Setup Ansible server

To install latest ansible on Ubuntu, see: [setup.md](setup.md)


## ansible.cfg

(?)adding hcloud collection:

(?)Starting galaxy role install process


sudo apt install python3-hcloud


create a new project in cloud.hetzner, create a new rw token

put it into:

tests/integration/cloud-config-hcloud.ini
[default]
hcloud_api_token=WIRWzEVjKwbhO4frlE80jMavu933cOAga3Pyl7OYourToken



vi ../host_vars/testserver.yml

```
---
hostname: "testserver"
cloudserver: "testserver"

# hcloud - Hetzner Cloud
h_server_location: "nbg1"
h_server_type: "cx11"
h_server_image: "ubuntu-22.04"
h_server_ssh_keys:
#  - anna_beispiel_salbei_19_pub

h_volume_name: "testserver-data"
h_volume_size: 10   #in GB
h_volume_format: "ext4"

```
ansible-playbook playbooks/h02-server-create.yml -i $HOME/.ansible/hosts --extra-vars "cloudserver=testserver"


## adding hcloud collection to ansible:


```
mc:~/ansible-git/ansible$ vi requirements.yaml

mc:~/ansible-git/ansible$ cat requirements.yaml
collections:
  - name: hetzner.hcloud

mc:~/ansible-git/ansible$ ansible-galaxy install -r requirements.yaml
Starting galaxy collection install process
Process install dependency map
Starting collection install process
...
...
hetzner.hcloud (2.5.0) was installed successfully

```


