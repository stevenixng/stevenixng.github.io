---
title: apcupsd
---

#### View apc battery status
    apcaccess status

#### Basic config file
```
## apcupsd.conf v1.1 ##
#UPSNAME
UPSCABLE usb
UPSTYPE usb
#POLLTIME 60
LOCKFILE /var/spool/lock
SCRIPTDIR /usr/local/etc/apcupsd
PWRFAILDIR /var/run
NOLOGINDIR /var/run
ONBATTERYDELAY 6
BATTERYLEVEL 5
MINUTES 3
TIMEOUT 0
ANNOY 300
ANNOYDELAY 60
NOLOGON disable
KILLDELAY 0
NETSERVER on
NISIP 0.0.0.0
NISPORT 3551
EVENTSFILE /var/log/apcupsd.events
EVENTSFILEMAX 10
UPSCLASS standalone
UPSMODE disable
STATTIME 0
STATFILE /var/log/apcupsd.status
LOGSTATS off
DATATIME 0
SENSITIVITY M
```
