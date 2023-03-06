# frankyw/home-server

This is a repository to version control and document my journey from one Ubuntu server with a multitude of apps running on it, to complete Docker containerization. Base system is Ubuntu 22 on a Proxmox LXC container. To create this config, I referenced [Smart Home Beginner](https://www.smarthomebeginner.com/category/home-server/) amongst other resources.

## Docker Containers

The following containers are being run:  

### Arr Stack

* [hotio/sonarr](https://hotio.dev/containers/sonarr/) - Management and automation of TV Show downloading.
* [hotio/radarr](https://hotio.dev/containers/radarr/) - Management and automation of Movie downloading.
* [hotio/unpackerr](https://hotio.dev/containers/unpackerr/) - Very nice container to handle compressed archives cleanly.
* [hotio/trackarr](https://hotio.dev/containers/trackarr/) - Get releases within seconds from IRC Announce Channels, and pass to Sonarr.
* [hotio/jackett](https://hotio.dev/containers/jackett/) - API Support for my trackers, to provide content to Sonarr and Radarr.

### LinuxServer

I like LinuxServer because they greatly simplify my life with support for user mappings (PGID, PUID), to avoid file permission problems with mounted host directories.

* [linuxserver/nginx](https://hub.docker.com/r/linuxserver/nginx/) - A good nginx/PHP container with alpine base and support for user/group identifiers.
* [linuxserver/deluge](https://hub.docker.com/r/linuxserver/deluge/) - A good Deluge container, which I used for manual downloading of files.
* [linuxserver/transmission](https://hub.docker.com/r/linuxserver/transmission/) - Another good linuxserver container, used as part of my automated media centre in conjunction with the *arr stack above.
* [linuxserver/unifi-controller](https://hub.docker.com/r/linuxserver/unifi-controller) - Latest stable of Ubiquiti Unifi controller for home network management.
* [linuxserver/duplicati](https://hub.docker.com/r/linuxserver/duplicati) - Duplicati container, backs up important files on my Linux server files to Google Drive.

### Other
* [traefik:latest](https://hub.docker.com/_/traefik) - Official Traefik container, reverse proxy to expose docker services over TLS using Let's Encrypt.
* [mariadb:latest](https://hub.docker.com/_/mariadb) - Official MariaDB image.
* [portainer/portainer](https://hub.docker.com/r/portainer/portainer) - Official Portainer image, container management made easy.
* [phpmyadmin/phpmyadmin](https://hub.docker.com/r/phpmyadmin/phpmyadmin) - Offical phpMyAdmin image for DB fiddling.
* [rednoah/filebot:node](https://hub.docker.com/r/rednoah/filebot/) - Headless Filebot container for media management (probably no longer needed after migration to *arr stack).
* [containrrr/watchtower](https://hub.docker.com/r/containrrr/watchtower) - Official Watchtower image to update all containers.
* [oznu/homebridge](https://hub.docker.com/r/oznu/homebridge/) - Provides Apple Homekit functionality to non-supported devices on my network.
* [oznu/cloudflare-ddns](https://hub.docker.com/r/oznu/cloudflare-ddns) - Cloudflare dynamic DNS updater.
* [google-containers/cadvisor](https://gcr.io/google-containers/cadvisor) - Collecting some stats for use by Prometheus.
* [mbentley/timemachine:smb](https://hub.docker.com/r/mbentley/timemachine) - Time Capsule for providing Time Machine backup functionality to all macOS devices.

## Configuration
I am using a Docker .env file, which contains all the variables found in the docker-compose.yml