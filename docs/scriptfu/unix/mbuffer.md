---
title: mbuffer
---

The fastest way to send data from one zfs dataset to another.
#### receive
    sudo mbuffer -4 -s 128k -m 1G -I 9090 | sudo zfs receive -F hellcat/books

#### send
    sudo zfs send -R tank/books@test | mbuffer -s 128k -m 1G -O 192.168.80.12:9090

#### Example output
    in @  0.0 kiB/s, out @  458 MiB/s, 71.3 GiB total, buffer  14% full
    summary: 71.5 GiByte in  2min 48.8sec - average of  434 MiB/s
