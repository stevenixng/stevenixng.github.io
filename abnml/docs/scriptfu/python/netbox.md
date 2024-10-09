---
title: netbox
---

#### search for devices in shell
``` py
import pynetbox

nb = pynetbox.api('https://netboxurl>', token="<token>")

devices = nb.dcim.devices.filter(site="<site>", tenant=["<tenant>"], status=["offline", "active"])

len(devices)

for device in devices:
    print(f"{device.id},{device.name}")
```
