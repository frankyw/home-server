# frankyw/home-server

This is a repository to version control and document my journey from one Ubuntu server with a multitude of apps running on it, to complete docker containerization. Base system is Ubuntu 20. To create this config, I referenced the [Smart Home Beginner](https://www.smarthomebeginner.com/category/home-server/) a lot.

## Docker Containers

The following containers are being run:

* [wiserain/flexget](https://hub.docker.com/r/wiserain/flexget/) - A small and well-maintained FlexGet container that includes the plugins I need. Used to run my [automated media centre](https://github.com/frankyw/flexget).
* [linuxserver/nginx](https://hub.docker.com/r/linuxserver/nginx/) - A good nginx/PHP container with alpine base and linuxserver support for user/group identifiers.
* [linuxserver/deluge](https://hub.docker.com/r/linuxserver/deluge/) - A good Deluge container, which I used for manual downloading.
* [linuxserver/transmission](https://hub.docker.com/r/linuxserver/transmission/) - Another good linuxserver container, which I used as part of my automated media centre.
* [linuxserver/unifi-controller](https://hub.docker.com/r/linuxserver/unifi-controller) - Latest stable of Ubiquiti controller.
* [rednoah/filebot:node](https://hub.docker.com/r/rednoah/filebot/) - Official Filebot container, used for automated media management.
* [mariadb:latest](https://hub.docker.com/_/mariadb) - Official MariaDB image for nginx backends.
* [traefik:latest](https://hub.docker.com/_/traefik) - Official Traefik container, exposes services over TLS.
* [portainer/portainer](https://hub.docker.com/r/portainer/portainer) - Official Portainer image, docker cluster management.
* [emby/embyserver:beta](https://hub.docker.com/r/emby/embyserver) - Official Emby beta container.
* [adguard/adguardhome](https://hub.docker.com/r/adguard/adguardhome) - Official AdGuard Home container, DNS blackhole for all that spam.
* [phpmyadmin/phpmyadmin](https://hub.docker.com/r/phpmyadmin/phpmyadmin) - Offical phpMyAdmin image for DB fiddling.
* [containrrr/watchtower](https://hub.docker.com/r/containrrr/watchtower) - Official Watchtower image to update all containers.
* [google-containers/cadvisor](https://gcr.io/google-containers/cadvisor) - Collecting some stats (which I may never use!)