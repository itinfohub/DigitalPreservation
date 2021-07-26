# Archivematica

[Archivematica](https://www.archivematica.org/en/) is an open source software package that powers digital preservation practices. It follows OAIS reference model and implement it in the package. 

## Installation

- We installed it on Ubuntu 20.04 LTS
- [Followed the docker container approach]()
- [Also installed with VirtualBox, Vagrant and Ansible](https://www.archivematica.org/en/docs/archivematica-1.13/admin-manual/installation-setup/installation/install-ansible/#install-ansible)

### Containers running 

|CONTAINER ID|   IMAGE |                                                 COMMAND   |      PORTS |
|:---|:---|:---|:---|
|7c9e2dca4d30|   hack_archivematica-mcp-client|                         "/src/src/MCPClient/…" | |
|ecdad2e6fee2|   hack_archivematica-dashboard |                         "/usr/local/bin/guni…" | 8000/tcp|
|a7adf9f8a138 |  docker.elastic.co/elasticsearch/elasticsearch:6.5.4|   "/usr/local/bin/dock…" | 9300/tcp, 127.0.0.1:62002->9200/tcp|
|6d486c58e769 |  hack_archivematica-mcp-server                   |  "/src/src/MCPServer/…"     | |
|d960410af992 |  hack_archivematica-storage-service   | "/usr/local/bin/guni…"                 |  8000/tcp |
|aebaadc594d0 |  artefactual/gearmand:1.1.18-alpine|                    "docker-entrypoint.s…" |   127.0.0.1:62004->4730/tcp |
|9b55d669080e |  artefactual/clamav:latest          |                   "/run.sh"              | 127.0.0.1:62006->3310/tcp |
|fe2021b7148e |  nginx:stable-alpine                 |                  "/docker-entrypoint.…" | 0.0.0.0:62080->80/tcp, 0.0.0.0:62081->8000/tcp |
|b9de4cbf1c78 |  artefactual/fits-ngserver:0.8.4      |                 "/usr/bin/fits-ngser…" | 127.0.0.1:62005->2113/tcp |
|396ec1676a68 |  percona:5.6                           |                "/docker-entrypoint.…" |   127.0.0.1:62001->3306/tcp |


### 
