---
title: borg backup
---

#### init a new backup
    borg init --encryption=repokey <user>@<server>:/<backupdir>/<computer>

#### manually create a first init backup with stats and progress
    borg create -s --progress <user>@<server>:/<backupdir>/<computer>::initial ~
