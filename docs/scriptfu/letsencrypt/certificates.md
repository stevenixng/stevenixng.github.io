---
title: certificates
---

#### read certificate
    openssl x509 -text -noout -in certificate.crt

#### small script to view information about cert
``` sh
#!/usr/bin/env sh

url=$1

if [ -z "${url}" ]; then
  echo "You need to provide a url"
  exit 1
fi

echo | openssl s_client -showcerts -servername "$url" -connect "$url":443 2>/dev/null | openssl x509 -inform pem -noout -text
```
