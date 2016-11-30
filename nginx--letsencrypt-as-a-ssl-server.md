# Nginx + Letsencrypt as a SSL Server

> Image: Debian 8 (Jessie)

## Installation

### Install nginx 
```
$ sudo apt-get update
$ sudo apt-get install nginx -y
```

### Install certbot

```
$ vim /etc/apt/sources.list.d/sources.list

# add the following line to sources.list and save
deb http://ftp.debian.org/debian jessie-backports main

$ sudo apt-get update
$ sudo apt-get install certbot -t jessie-backports
```

## Generate SSL Certificate

Generate SSSL certificate with certbot
```
$ certbot certonly --standalone -d <YOUR_DOMAIN>
```

## Nginx Configuration

Edit nginx configuration
```
# nginx conf
...
listen 443 ssl default_server;
listen [::]:443 ssl default_server;

ssl_certificate /etc/letsencrypt/live/<YOUR_DOMAIN>/fullchain.pem;

ssl_certificate_key /etc/letsencrypt/live/<YOUR_DOMAIN>/privkey.pem;
...
```

## References
- https://backports.debian.org/Instructions/
- https://certbot.eff.org/all-instructions/#debian-8-jessie-nginx!
