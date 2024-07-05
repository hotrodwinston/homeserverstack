OpenHAB

version: '2.2'

services:
  openhab:
    image: openhab/openhab:latest
    restart: unless-stopped
    network_mode: host
    cap_add:
      - NET_ADMIN
      - NET_RAW
      - SYS_ADMIN
    volumes:
      - /etc/localtime:/etc/localtime:ro
      - /etc/timezone:/etc/timezone:ro
      - /srv/dev-disk-by-uuid-974cfdef-5396-4352-aea7-58a8d718a4c7/compose/openhab_addons:/openhab/addons
      - /srv/dev-disk-by-uuid-974cfdef-5396-4352-aea7-58a8d718a4c7/compose/openhab_conf:/openhab/conf
      - /srv/dev-disk-by-uuid-974cfdef-5396-4352-aea7-58a8d718a4c7/compose/openhab_userdata:/openhab/userdata
    environment:
      CRYPTO_POLICY: unlimited
      EXTRA_JAVA_OPTS: -Duser.timezone=America/Chicago
      OPENHAB_HTTP_PORT: 8080
      OPENHAB_HTTPS_PORT: 8443
      USER_ID: 9001
      GROUP_ID: 9001
    privileged: true 


    create user with id above before deploy

  Gluetun/qbittorrent from https://github.com/JamesTurland/JimsGarage/tree/main/Torrent-VPN
  with protonvpn setup from https://github.com/qdm12/gluetun-wiki/blob/main/setup/providers/protonvpn.md

  note: For anyone hosting qbittorrent container on their NAS. This is added in a new update or something. If qBittorrent detects a password was not set, instead of allowing you to login using the default password: adminadmin. it will produce a random password, you can find it in the container log.

The message should be:

"The WebUI administrator password was not set. A temporary password is provided for this session: _your_password_here_"
