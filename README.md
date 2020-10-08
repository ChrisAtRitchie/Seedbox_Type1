# Seedbox_Type1

Revision: 0.0 (alpha one)

Date: 08/10/2020

Seedbox type 1, is a docker compose context, that will spin up a number of containers that together function as a seedbox.

it contains the necessary files to be executable with only two operations after downloading this repository
  1: Update the .env file to replace the necessary variables
  2: execute the command 'docker compose up'

It includes the following containers

- Alpine linux, as a base of operations for file manipulation or other command line scripting.
- Pureftpd, to provide TLS protected FTP file transfer mechanisms.
- Deluge, as an engine and web/daemon front end for processing torrents.
- Firefox, as a VNC accessible web browser, used to browse the internet for torrents, and also access web-based internal services such as the deluge web GUI.
- The following torrent automation and management tools
  - jackett
  - sonarr
  - radarr
  - lidarr
  - bazarr

The access port mappings are assigned dynamically based on the .env file, but the following container ports are available
  - Port 22, for SSH CLI access, and SFTP file transfer access.
  - Ports 989 and 990, for FTPS file transfer access.
  - Port 5900, for VNC remote access to the firefox browser.

The port (TCP/UDP) mapping for incoming connections to Deluge, are assigned the same number dynamically for both host and container, in the range of 58000 to 58999.
