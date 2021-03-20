# rancher-server-install

````
docker run -d --name=rancher --restart=unless-stopped -p 80:80 -p 443:443 --privileged rancher/rancher:latest --acme-domain ranchertest.int.vmar.se
````
