
# API / ansible  for HETZNER / hcloud

## API

### list volumes

curl -H "Authorization: Bearer $API_TOKEN" "https://api.hetzner.cloud/v1/volumes"

### detach volume $ID

curl X POST -H "Authorization: Bearer $API_TOKEN" "https://api.hetzner.cloud/v1/volumes/${ID}/actions/detach"

### delete volume

curl X DELETE -H "Authorization: Bearer $API_TOKEN" "https://api.hetzner.cloud/v1/volumes/${ID}/"

### view servers

curl -H "Authorization: Bearer $API_TOKEN" "https://api.hetzner.cloud/v1/servers"

curl -H "Authorization: Bearer $API_TOKEN" "https://api.hetzner.cloud/v1/servers/${ID}"

### delete server
get IDs:

 curl -H "Authorization: Bearer $API_TOKEN" "https://api.hetzner.cloud/v1/servers/"   |grep -B1 name |grep id

remove server

 curl -X DELETE -H "Authorization: Bearer $API_TOKEN" "https://api.hetzner.cloud/v1/servers/${ID}/"


## ansible

### install a server
create a config file in host-vars/servername.yml

ansible-playbook playbooks/h02-server-create.yml --skip-tags add-disk --extra-vars "cloudserver=t2-centos1"

### delete a server

ansible-playbook playbooks/h02-server-remove.yml -t list,remove --extra-vars "cloudserver=t1-debian12"

or

ansible-playbook ~/ansible-git/ansible/playbooks/h02-server-remove.yml --extra-vars "cloudserver=t1-debian12" 


