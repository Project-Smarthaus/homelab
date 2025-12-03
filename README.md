# Create initial network
podman network create \
  --driver bridge \
  --subnet 10.0.69.0/24 \
  --gateway 10.0.69.1 \
  reverse-proxy

podman network create \
  --driver bridge \
  edge

podman-compose -f ferretdb.compose.yaml up -d --force-recreate
