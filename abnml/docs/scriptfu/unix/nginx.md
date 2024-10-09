---
title: nginx
---

#### host a static site
    server {
        listen 80;
        listen [::]:80;
        server_name wiki.br.abnml.com;
        return 301 https://wiki.br.abnml.com$request_uri$is_args$args;
    }
    
    server {
        listen 443 ssl;
        server_name wiki.br.abnml.com;
        ssl_certificate /etc/letsencrypt/live/wiki.br.abnml.com/fullchain.pem;
        ssl_certificate_key /etc/letsencrypt/live/wiki.br.abnml.com/privkey.pem;
        ssl_trusted_certificate /etc/letsencrypt/live/wiki.br.abnml.com/chain.pem;
        access_log /var/log/nginx/wiki.br.abnml.com.access.log;
        error_log /var/log/nginx/wiki.br.abnml.com.error.log;
        root /srv/www/wiki.br.abnml.com/public_html;
    
        error_page 404 /srv/www/wiki.br.abnml.com/public_html/404.html;
    }
