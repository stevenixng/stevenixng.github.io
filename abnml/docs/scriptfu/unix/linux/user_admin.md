---
title: User admin
---

#### add new user
    useradd -m -G sudo -p <password> <username>

#### add new service account
    sudo useradd --system --no-create-home ampache

#### add new user with custom home dir
    sudo useradd -m -d /opt/username username

#### add user to group
    sudo usermod -a -G media pi

#### make a new group with gid
    sudo groupadd -g 1010 media

#### run as another user that has /bin/nologin set
    su -m <user> -c "<command>"

