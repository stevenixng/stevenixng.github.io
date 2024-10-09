---
title: Remote bare repo
---

#### Make a new bare repo
    ssh <username>@<host> 'git init --bare ~/git/dotfiles.git'

#### Push to the new repo
    git push <username>@<host>:~/git/dotfiles main
