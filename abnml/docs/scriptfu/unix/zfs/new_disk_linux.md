---
title: new disk (linux)
---

#### install parted
    apt install parted

#### this will give us 'partprobe' so we can have linux rescan disks
    partprobe

#### check out disk id
    ls -lh /dev/disk/by-id

#### set GPT table
    sudo parted /dev/disk/by-id/<disk>
    (parted) mklabel GPT

#### view disks by ID
    ls /dev/disk/by-id
