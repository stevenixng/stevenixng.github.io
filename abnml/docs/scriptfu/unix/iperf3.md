---
title: iperf3
---

Perform network throughput tests.

  *  [iperf3 manpage](https://linux.die.net/man/1/iperf)

#### set up a server
    iperf3 -s -p 30001

#### connect with client
    iperf3 -c <host> -p 30001
