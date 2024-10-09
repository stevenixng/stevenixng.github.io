---
title: Dell PERC
---

### disks

#### check vdisks
    omreport storage vdisk

#### check physical disks belonging to vdisk
    omreport storage pdisk controller=0 vdisk=0

#### check all physical disks
    omreport storage pdisk controller=0

#### blink disk
    omconfig storage pdisk action=blink controller=0 pdisk=0:1:6
    omconfig storage pdisk action=unblink controller=0 pdisk=0:1:6

#### find available slots
    omreport storage controller controller=0 info=pdslotreport

#### clear foreign config
    omconfig storage controller action=clearforeignconfig controller=0

#### discard preserved cache
    omconfig storage controller action=discardpreservedcache controller=0 force=enabled

#### create new morrored vdisk
    omconfig storage controller action=createvdisk controller=0 raid=r1 size=max pdisk="0:1:6,0:1:7"
    omconfig storage controller action=createvdisk controller=0 raid=r1 size=max pdisk="0:1:0,0:1:7"
