---
authors: [stevenix]
date: 2024-10-05
draft: true
---

# How I stay on IRC

I used to use [IRCCloud](https://www.irccloud.com/) and it works great! But in an effort to try to self host and save money, I set up a VM running Weechat and its relay. Here I'll detail how I have that configured.

<!-- more -->

## Weechat configuration
I have three ways I can connect to it:

 * SSH to the server and do a `tmux attach`.
 * For web based access use I use [Glowing Bear](https://latest.glowing-bear.org/). Glowing bear also works great on mobile browsers.
 * On IOS I use [Lith](https://github.com/LithApp/Lith). You will need to set up testflight.
 * For Android, you can use [weechat-android](https://github.com/ubergeek42/weechat-android).

## Configure tmux and weechat
First get tmux and weechat installed. I'm using weechat 3.8 and tmux 3.3a. Configuring tmux and weechat are beyond the scope of this guide, but I suggest you follow the [weechat quick start guide](https://weechat.org/files/doc/weechat/stable/weechat_quickstart.en.html) to get you through configuring weechat for the network and channels you want to join. You'll also need to [configure the weechat relay](https://weechat.org/files/doc/weechat/stable/weechat_user.en.html#relay)

## Autostart tmux with weechat on boot with the systemd service
```
[Unit]
# If for some reason you need to run multiple tmux services, then please see
# https://superuser.com/questions/1581577/running-two-tmux-sessions-as-systemd-service/1582196#1582196
Description=Tmux weechat server

[Service]
Type=forking
User=stevenix
ExecStart=/usr/bin/tmux new-session -d -s weechat -n weechat "weechat"
ExecStop=/usr/bin/tmux kill-server

[Install]
WantedBy=multi-user.target
```

## letsencrypt post renewal hook
To use glowingbear and other relay clients, you'll want to set up an ssl certificate. You'll want to set up certbot or acme.sh (also beyond the scope of this particular guide) but I'll include a post renewal hook below to update weechat with a new cert when its renewed. I'm using DNS validation so that I don't have to expose anything using port forwarding. 
```
#!/bin/bash

TMUXUSER="stevenix"
SSLPATH="/home/stevenix/.weechat/ssl/relay.pem"
SSLURL="chatter.abnml.com"

# copy the letsencrypt cert to the weechat dir
sudo cat /etc/letsencrypt/live/"$SSLURL"/{fullchain,privkey}.pem > "$SSLPATH"

# have weechat reload the certificate
su "$TMUXUSER" -c 'tmux send-keys -t weechat:weechat.0 "/relay sslcertkey" ENTER'
```

## Configure Glowingbear
TODO

## Configure Lith
TODO
