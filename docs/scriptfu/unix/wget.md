---
title: wget
---

#### options
    -r recursive
    -l7 level depth
    -np no parent
    -nH no host directories
    --cut-dirs=1 ignore directories
    -A acceptlist of file types to download
    --no-verbose clean up some of the noise

#### Fetch PDFS and XLSX files recursively from site
    wget -r -l7 -np -nH --cut-dirs=1 -A "*.pdf, *.xlsx" https://<somewebsite>/ --no-verbose
