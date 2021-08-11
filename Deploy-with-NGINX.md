## ⚠ This is still a WIP

**Make sure to have followed the installation guide. This guide will show you have to deploy using [Nginx](https://nginx.org/en/)**

# Getting started

## Requirements

- Linux VPS (Ubuntu)
- Installed SnailyCAD

## Installing NGINX

Run the following commands:

1. `sudo apt update`
2. `sudo apt install nginx`

## Setting up a host

create a new file in `/etc/nginx/sites-available/` called: `example.com.conf`, - replace example.com with your domain! 
paste this into `/etc/nginx/sites-available/example.com.conf`

```
server {
    listen 80;
    server_name example.com;
    access_log /var/log/nginx/snailycad.app-access.log;
    error_log  /var/log/nginx/snailycad.app-error.log error;

    location / {
        proxy_pass http://localhost:3030;
        proxy_read_timeout 90;
        proxy_http_version 1.1;
        proxy_set_header X-Forwarded-For $remote_addr;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
    }
}
```
now do this: `sudo ln -s /etc/nginx/sites-available/example.com.conf /etc/nginx/sites-enabled/example.com.conf` while once again replacing example.com.conf with your domain name!
finnally do:
`sudo systemctl restart nginx`
then visit your website and it should work!

## SSL SETUP ##
enter the follwing commands:

`sudo apt update && apt install -y certbot && apt install -y python3-certbot-nginx -y`

now enter
`certbot certonly --nginx -d example.com` make sure to replace example.com with your domain!
finally put this into `/etc/nginx/sites-available/example.com.conf`
 Replace example.com with your domain again!
```
server {
    listen 80;
    server_name example.com;
    return 301 https://$server_name$request_uri;
}
server {
    listen 443 ssl;
    server_name domainname;
    access_log /var/log/nginx/snailycad.app-access.log;
    error_log  /var/log/nginx/snailycad.app-error.log error;
    # SSL Configuration
    ssl_certificate /etc/letsencrypt/live/example.com/fullchain.pem;
    ssl_certificate_key /etc/letsencrypt/live/example.com/privkey.pem;
    ssl_session_cache shared:SSL:10m;
    ssl_protocols TLSv1.2 TLSv1.3;
    ssl_ciphers "ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:DHE-RSA-AES128-GCM-SHA256:DHE-RSA-AES256-GCM-SHA384";
    ssl_prefer_server_ciphers on;
    
    location / {
        proxy_pass http://localhost:3030;
        proxy_read_timeout 90;
        proxy_http_version 1.1;
        proxy_set_header X-Forwarded-For $remote_addr;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
    }
}
```