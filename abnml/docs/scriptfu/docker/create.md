---
title: docker app
---

#### build image
    docker build -t <tagname> .

#### run image temporarily
    sudo docker run --rm -it -p 8080:5000 --name spyglass-frontend <tagname>
