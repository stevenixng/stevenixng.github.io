---
title: SSH
author: Steve Anderson <stevenix@protonmail.com>
---

#### diff over ssh
    diff foo <(ssh server 'cat foo')
    diff <(ssh server1 'cat foo') <(ssh server2 'cat foo')

#### poor mans ssh tunnel
    <local port> <target> <remote port> <bastion>
    ssh -L 8000:example.com:443 mybastionhost.com
