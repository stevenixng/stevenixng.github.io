---
title: zpool command
---

### new pool
#### create new pool
    zpool create tank <dev0> <dev1>

#### add a new vdev to existing pool
    zpool add tank raidz1 <dev2> <dev3>

#### get general status
    zpool status

#### list zpools
    zpool list

### history
#### get command history
    zpool history

#### user initiated
    zpool history -i

#### long format
    zpool history -l

### scrubs
#### start scrub
    sudo zpool scrub tank

#### pause scrub
    sudo zpool scrub -s tank

### replace disks
#### replace a disk.
    sudo zpool replace <poolname> <missing_guid> <new_dev>

#### Monitor the progress of the resilvering operation
    zpool status -x

#### get iostat
    zpool iostat tank 2
