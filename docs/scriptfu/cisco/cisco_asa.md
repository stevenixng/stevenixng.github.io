---
title: Cisco ASA
---

#### backup asa config
    copy running-config disk0:/running-config_backup.txt

#### scp config
    scp -O <host>:disk0:running-config_backup.txt .

#### list asa users
    show running-config username

#### change asa passwords
    username <username> password <password> priv 15

### Debug
#### dap
    debug dap error
    debug dap trace 2

#### site-to-site
##### IKEv1
    debug crypto condition peer X.X.X.X
    debug crypto ikev1 200

##### IKEv2:
    debug crypto condition peer X.X.X.X
    debug crypto ikev2 platform 100
    debug crypto ikev2 protocol 100

#### show conditions so we can remove
    show debug
