---
title: user management
---

#### create service account
    sudo pw adduser proxmox -u 1005 -s /usr/sbin/nologin

#### create sftp only user
    adduser <username>
    pw groupmod sftpdump -m <username>
    pw usermod <username> -s /sbin/nologin
