---
title: Disable power button
---

#### Edit `/etc/systemd/logind.conf`
    # update HandlePowerKey to "ignore"
    HandlePowerKey=ignore

#### Restart systemd-logind
    sudo systemctl restart systemd-logind
