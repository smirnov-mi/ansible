
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



