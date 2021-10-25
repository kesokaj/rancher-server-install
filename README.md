# rancher-server-install

````
docker run -d --name=rancher --restart=unless-stopped -p 80:80 -p 443:443 --privileged rancher/rancher:v2.5.7 --acme-domain vks.vmar.xyz

admin / 9aHqbbHvhLQnQcX7dHfdha9gKNaPGvNXjSh5evpwD5rMKmN8


version: "3.6"
services:
  rancher:
    image: "rancher/rancher:v2.5.7"
    container_name: rancher
    hostname: rancher
    privileged: true
    restart: unless-stopped
    ports:
    - "80:80"
    - "443:443"
    volumes:
    - /opt/rancher/auditlog:/var/log/auditlog
    - /opt/rancher/data:/var/lib/rancher
    environment:
    - AUDIT_LEVEL=1
    command: "--acme-domain vks.vmar.xyz"

````
