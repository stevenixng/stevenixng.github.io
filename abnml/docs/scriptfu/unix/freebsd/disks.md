---
title: disks
---

#### list disks
    geom disk list
    camcontrol devlist

#### find serial
    sudo camcontrol identify /dev/da7 | grep serial


##### monitor disk i/o
    gstat
    iostat

#### show controller info
    sudo mpsutil show all
