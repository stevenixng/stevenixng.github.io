---
title: acme.sh freebsd
---

# acme.sh

Configs and certs can be found in `~/.acme.sh/`

#### upgrade acme.sh
    acme.sh --upgrade

#### issue first certificate using he dns
    acme.sh --issue -d abnml.com -d '*.abnml.com' --dns dns_he --server letsencrypt

#### install cronjob
    acme.sh --install-cronjob

#### list certs and dates
    acme.sh --list

#### set [notifications](https://github.com/acmesh-official/acme.sh/wiki/notify)
    acme.sh --set-notify --notify-hook mailgun --notify-level 2 --notify-mode 0
