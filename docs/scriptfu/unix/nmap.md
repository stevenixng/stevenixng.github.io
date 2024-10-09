---
title: nmap
---

#### quick portscan of a subnet and display readably on terminal
    nmap -sn 192.168.1.0/24 -oG -

#### identify service on port
    nmap -sV -p80 192.168.1.1

#### identify OS
    sudo nmap -O 192.168.1.1

#### uses vulscan script to check target services for vulnerabilities.
    alias nmap_check_for_vulns="nmap --script=vuln"
