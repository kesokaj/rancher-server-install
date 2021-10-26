# rancher-server-install

````
docker run -d --name=rancher --restart=unless-stopped -p 80:80 -p 443:443 --privileged rancher/rancher:stable --acme-domain <your domain>

version: "3.6"
services:
  rancher:
    image: "rancher/rancher:stable"
    container_name: rancher
    hostname: rancher
    privileged: true
    restart: unless-stopped
    ports:
    - "80:80"
    - "443:443"
    volumes:
    - /opt/rancher/auditlog:/var/log/auditlog:rw
    - /opt/rancher/data:/var/lib/rancher:rw
    environment:
    - AUDIT_LEVEL=1
    command: "--acme-domain <your domain>"

````
