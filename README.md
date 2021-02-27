# frankyw/home-server

This is a repository to version control and document my journey from one Ubuntu server with a multitude of apps running on it, to complete Docker containerization. Base system is Ubuntu 20. To create this config, I referenced [Smart Home Beginner](https://www.smarthomebeginner.com/category/home-server/) quite a bit.

## Docker Containers

The following containers are being run:

* [traefik:latest](https://hub.docker.com/_/traefik) - Official Traefik container, reverse proxy to expose docker services over TLS using Let's Encrypt. 
* [wiserain/flexget](https://hub.docker.com/r/wiserain/flexget/) - A small and well-maintained FlexGet container that includes the plugins I need. Used to run my [automated media centre](https://github.com/frankyw/flexget).
* [linuxserver/nginx](https://hub.docker.com/r/linuxserver/nginx/) - A good nginx/PHP container with alpine base and linuxserver support for user/group identifiers.
* [linuxserver/deluge](https://hub.docker.com/r/linuxserver/deluge/) - A good Deluge container, which I used for manual downloading of files.
* [linuxserver/transmission](https://hub.docker.com/r/linuxserver/transmission/) - Another good linuxserver container, used as part of my automated media centre in conjunction with Flexget and Filebot.
* [linuxserver/unifi-controller](https://hub.docker.com/r/linuxserver/unifi-controller) - Latest stable of Ubiquiti Unifi controller for home network management.
* [rednoah/filebot:node](https://hub.docker.com/r/rednoah/filebot/) - Headless Filebot container, used for automated extraction of downloads via REST calls.
* [mariadb:latest](https://hub.docker.com/_/mariadb) - Official MariaDB image.
* [portainer/portainer](https://hub.docker.com/r/portainer/portainer) - Official Portainer image, docker container management made easy.
* [emby/embyserver:beta](https://hub.docker.com/r/emby/embyserver) - Official Emby beta container, home media server.
* [adguard/adguardhome](https://hub.docker.com/r/adguard/adguardhome) - Official AdGuard Home container, DNS blackhole for all that spam.
* [phpmyadmin/phpmyadmin](https://hub.docker.com/r/phpmyadmin/phpmyadmin) - Offical phpMyAdmin image for DB fiddling.
* [linuxserver/duplicati](https://hub.docker.com/r/linuxserver/duplicati) - Duplicati container, backs up important files on my Linux server files to Google Drive.
* [containrrr/watchtower](https://hub.docker.com/r/containrrr/watchtower) - Official Watchtower image to update all containers.
* [oznu/homebridge](https://hub.docker.com/r/oznu/homebridge/) - Provides Apple Homekit functionality to non-supported devices on my network.
* [oznu/cloudflare-ddns](https://hub.docker.com/r/oznu/cloudflare-ddns) - Cloudflare dynamic DNS updater.
* [google-containers/cadvisor](https://gcr.io/google-containers/cadvisor) - Collecting some stats for use by Prometheus.
* [prom/prometheus](https://hub.docker.com/r/prom/prometheus/) - Prometheus stats collection, which I used to collect metrics on docker containers and the host machine. Used in conjunction with Grafana cloud.
* [mbentley/timemachine:smb](https://hub.docker.com/r/mbentley/timemachine) - Time Capsule for Time Machine backup onto network storage.

## Configuration

I am using a Docker .env file, which contains all the variables found in the docker-compose.yml