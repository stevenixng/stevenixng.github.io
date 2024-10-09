---
title: bhyve
source: https://github.com/churchers/vm-bhyve/blob/master/README.md
---

#### create vm
    sudo vm create <vmname>

#### transfer proxmox raw image
    sudo dd if=/dev/mapper/pve-vm--100--disk--0 bs=1M | ssh beefcake 'dd of=/hellcat/backup/rstudio.img'

#### list vms
    sudo vm list

#### get console
    sudo vm console rstudiotest

#### exit console
    ~ + Ctrl-D

### check partition of disk
#### make vnode
    sudo mdconfig -a -t vnode -u 0 -f /hellcat/bhyve/rstudiotest/disk0.img

#### detach
    sudo mdconfig -d -u /dev/md0

#### find device
    sudo mdconfig -l

#### list partitions 
    sudo fdisk md0
    gpart list md0
