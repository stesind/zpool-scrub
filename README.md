# zpool-scrub-weekly
Service and Timer for zpool scrub on Ubuntu

## Install on Ubuntu
- Clone this repository, change into the directory zpool-scrub-weekly
- Install and enable timer and service file in /etc/systemd/system using:
```sh
install -m 644 -o root -g root zpool-scrub@.service /etc/systemd/system
install -m 644 -o root -g root zpool-scrub@.timer /etc/systemd/system

systemctl daemon-reload
systemctl enable --now zpool-scrub@<POOLNAME>.timer
```
Replace &lt;POOLNAME&gt; with the name of your pool.
Keep in mind that the path is /sbin/zpool in Ubuntu. On Arch Linux it is /usr/sbin/zpool. One has to change the service file accordingly if not used in Ubuntu. If you are unsure about the location, use:
  ```sh
  which zpool
  ```
