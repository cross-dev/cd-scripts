Base minimal ArchLinux Docker image

## Environment

* EC2 micro-instance
* ArchLinux AMI
* Remove `ec2` repository from `/etc/pacman.conf`
* `pacman -Sy expect docker`
* Make sure `docker` systemd-unit is enabled and running
* A reboot might be necessary after docker installation
* User data has to be configured with the information to login to the Docker Hub

```
HUB_USER=...
HUB_PASSWORD=...
HUB_EMAIL=...
```

* Clone [docker](https://github.com/docker/docker) source code under `/usr/src/docker`.

## Running

Simply execute `archlinux` script. Upon success it will push `crossdev/archlinux` to the
registry.
