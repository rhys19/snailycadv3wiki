## ⚠ This is still a WIP

**Make sure to have followed the installation guide. This guide will show you have to deploy using [Nginx](https://nginx.org/en/)**

# Getting started

## Requirements

- Linux VPS (Ubuntu) with ssh access (Root)
- Installed Plesk

## Setting up plesk

You'll need SSH Access to install the cad!

Run the installation guide in a folder not in the /var/www/vhosts ex: /home/snaily-cadv3

make sure you created your site via plesk first!


## Setting up the proxy!

go under your website & goto `Apache & NGINX settings` then scroll to the bottom and paste the following inside of `Additional nginx directives`
remember to replace example.com with your domain!
```
    location / {
        proxy_pass http://localhost:18144;
        proxy_read_timeout 90;
        proxy_http_version 1.1;
        proxy_set_header X-Forwarded-For $remote_addr;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
    }
```


then your done!