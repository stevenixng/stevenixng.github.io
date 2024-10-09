---
title: certbot debian
---

#### Create TXT record on hurricane electric
    _acme-challenge.abnml.com

#### Install certbot on Debian 12
    sudo snap install --classic certbot
    sudo snap set certbot trust-plugin-with-root=ok
    sudo snap install certbot-dns-multi
    sudo snap connect certbot:plugin certbot-dns-multi

#### Create `/etc/letsencrypt/dns-multi.ini` file
    dns_multi_provider = hurricane
    HURRICANE_TOKENS=abnml.com:<token>

#### Update permissions on `dns-multi.ini`
    sudo chmod go-r /etc/letsencrypt/dns-multi.ini

#### Request certonly
    sudo /snap/bin/certbot certonly -a dns-multi --dns-multi-credentials=/etc/letsencrypt/dns-multi.ini -d "abnml.com" -d "*.abnnml.com"
