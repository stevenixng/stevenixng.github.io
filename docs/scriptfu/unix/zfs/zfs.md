---
title: zfs command
---

### properties
#### get all properties
    zfs get all tank

### snapshots
#### list snapshots
    zfs list -t snapshot

#### create new snapshot
    sudo zfs snapshot -r tank@<snapshotname>

### datasets
#### create a new dataset
    sudo zfs create tank/home

#### change mount point (for home dir)
    sudo zfs set mountpoint=/home/ tank/home

### quotas
#### check userquotas
    sudo zfs userspace tank/home
    sudo zfs get userquota@username tank/home

#### set quota
    zfs set userquota@student1=10G students/compsci

### share
#### list shares
    sudo zfs get sharenfs

#### set shares
    zfs set sharenfs='on,192.168.81.35' tank/downloads
