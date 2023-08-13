docker build --platform linux/amd64 -f Dockerfile -t matrix009/client_container:v1.0.0 .

docker build --platform linux/amd64 -f Dockerfile.ssh -t matrix009/ssh_container:v1.0.0 .

docker run -d --name client_container matrix009/client_container:v1.0.0

docker run -it --name client_container2 matrix009/client_container:v1.0.0 /bin/bash

docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' ssh_container

ssh username@ssh_container_ip -p 22# ssh_communication
