# Docker registry + automatic let's encrypt certificate

This project showcases automatic docker registry creation and deployment with automatic https (credits to https://github.com/smashwilson/lets-nginx ).


There is a modified version of ```lets-nginx/templates/vhost.sample.conf``` with added docker registry location v2 rules.

This registry uses basic auth, in this example file ```password_registry``` contains 

* username: demo
* password: demo

Change this htpasswd with your user and password of choice ( useful link to generate pwd http://www.htaccesstools.com/htpasswd-generator/ )

### Registry browser

In this example we are using https://hub.docker.com/r/hyper/docker-registry-web/ as UI to browse uploaded images into docker registry.


### Start Registry

Make sure to have your registry.domain.tld A record pointing to your server ip address

Copy and customize ```.env``` and ```password_registry``` files

```bash
cp .env.example .env
cp password_registry_example password_registry
```

Start registry with:

```bash
docker-compose up -d
```

