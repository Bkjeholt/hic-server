# hic-server
## Introduction

## docker run command
``` 
docker run -d \
            --restart=always \
            --name mysql-backup-service \
            --link <The mysql container name>:mysql \
            --env FTP_HOST_ADDR=<Path to the ftp-server> \
            --env FTP_USER_NAME=<User name defined by the ftp-server> \
            --env FTP_PASSWORD=<Password defined by the ftp-server> \
            --env FTP_BACKUP_BASE_DIR=<Base path within the ftp-server> \
            --env MYSQL_BACKUP_INTERVALL="12" \
            --env DOCKER_CONTAINER_NAME=<A system unique container name> \
            bkjeholt/mysql-backup-ftp:<Docker image tag>
```
## Environment variables
Environment variable | Description | Example
---------------------------|----------------|--------------------------------------------------
FTP_HOST_ADDR | Ethernet address to the FTP-server | FTP_HOST_ADDR="ftp-server.com"
FTP_USER_NAME | FTP-server user name | FTP_USER_NAME="db_user"
FTP_PASSWORD | FTP-server password | FTP_PASSWORD="Ft54RfeDFrG45-R45Df"
FTP_BACKUP_BASE_DIR | Path to the backup-archive within the ftp-server | FTP_BACKUP_BASE_DIR="Backup/"
FTP_BACKUP_FILENAME | File name formated according to the linux command ``` date ``` | FTP_BACKUP_FILENAME="+backup-%g%m%d-%H%M.tar" This will give a filename like: ``` backup-170123-1713.tar```
DOCKER_CONTAINER_NAME | The container name, should be the same as stated in the --name parameter  | DOCKER_CONTAINER_NAME="hic-mysql-backup"

### Mysql linking

## Docker image

There are two variants of docker images on the https://hub.docker.com/bkjeholt/mysql-backup-ftp . 
One compilation for standard x86 based systems and one for RaspberryPi and probably other Arm-based systems as well.

## Docker image tag

The tag consist of a couple of fields
## Docker container name
