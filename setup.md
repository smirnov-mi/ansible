# Setting up the ansible server


## install latest ansible 

**Make sure** you use the ansible repo, **not** the OS one.

https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html#installing-ansible-on-ubuntu


```
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible

# might need to re-run, due to dpkg error:
sudo apt --fix-broken install

```

## add HCLOUD collection

https://github.com/ansible-collections/hetzner.hcloud
https://github.com/ansible-collections/hetzner.hcloud/blob/main/examples/use-refresh-inventory.yml


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


### install hcloud-python module

https://hcloud-python.readthedocs.io/en/stable/installation.html

https://github.com/hetznercloud/hcloud-python


```
xxx@rancher-mc:~/ansible-git$ apt install pip

xxx@rancher-mc:~/ansible-git$ git clone git@github.com:hetznercloud/hcloud-python.git

xxx@rancher-mc:~/ansible-git$ sudo pip install ./hcloud-python
```


 
### add Ansible Collection: hetzner.hcloud

https://github.com/ansible-collections/hetzner.hcloud


```
ansible-galaxy collection install hetzner.hcloud
```
or 
```
ansible-galaxy collection install hetzner.hcloud:==2.5.0 --force


Installing 'hetzner.hcloud:2.5.0' to '/home/xxx/.ansible/collections/ansible_collections/hetzner/hcloud'
Downloading https://galaxy.ansible.com/api/v3/plugin/ansible/content/published/collections/artifacts/hetzner-hcloud-2.5.0.tar.gz 


```


