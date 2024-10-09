---
title: motd
manpage: https://man.freebsd.org/cgi/man.cgi?motd
---

I takes more than just modifying `/etc/motd` on a freebsd system now to modify the motd.
You need to modify the template file then restart the service. During system startup, the kernel 
version is prepended to `/etc/motd.template` and then written to `/var/run/motd`.

#### Update the motd
  * edit `/etc/motd.template`

#### restart the motd service
    service motd restart
