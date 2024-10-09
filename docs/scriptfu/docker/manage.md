---
title: manage
---

#### get shell on docker container
    docker exec -it <container_id> sh

#### start new container in daemon mode
    docker run -d -p 8082:5000 --name <name> <image>

#### rename container
    docker rename <target> <new_name>

#### modify restart policy
    docker update --restart unless-stopped <container>

