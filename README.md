# hic-server
## Introduction
To execute this, the following files needs to be copied to an unique directory:
``` 
 .env
 docker-compose-rpi.yml
 docker-compose-x86.yml
```
Rename applicable one of these ``` docker-compose-XXX.yml ``` files according to below.
``` 
mv docker-compose-rpi.yml docker-compose.yml
```
or 
``` 
mv docker-compose-x86.yml docker-compose.yml
```

## run command
To start this server with the included services. Write the following command:
``` 
docker-compose up -d
```
## .env file
Configuration of the server will be done via the ```.env``` file that should be stored in the same directory as the ```docker-compose.yml``` file. 

A basic contents of that file is shown below:
```
MYSQL_ROOT_PASSWORD=RgT4De3%rTTge35yY7
MQTT_IP_ADDR=192.168.1.10
MQTT_PORT_NO=1883
PMA_PORT_NO=18085
FTP_HOST=ftp-server-com
FTP_USER=bamse
FTP_PASSWORD=ErFRtg54r-rtTGe4JklP
FTP_BACKUP_BASE_DIR=Backup
FTP_BACKUP_INTERVALL=12
DEBUG=0
```
## Environment variables
Environment variable | Description | Example
---------------------------|----------------|--------------------------------------------------
MYSQL_ROOT_PASSWORD | The root password chosen at creation of the mysql container | MYSQL_ROOT_PASSWORD=RgT4De3%rTTge35yY7 
 | | 
MQTT_IP_ADDR | The adress to the MQTT broker | MQTT_IP_ADDR=192.168.1.10
MQTT_PORT_NO | Port number used by the MQTT broker | MQTT_PORT_NO=1883
 | | 
PMA_PORT_NO | Port number used for external access of phpmyadmin | PMA_PORT_NO=8080
 | | 
FTP_HOST | Ethernet address to the FTP-server | FTP_HOST="ftp-server.com"
FTP_USER | FTP-server user name | FTP_USER="db_user"
FTP_PASSWORD | FTP-server password | FTP_PASSWORD="Ft54RfeDFrG45-R45Df"
FTP_BACKUP_BASE_DIR | Path to the backup-archive within the ftp-server | FTP_BACKUP_BASE_DIR="Backup/"
FTP_BACKUP_INTERVALL=12 | The timeintervall (in hours) between every backup attempt | FTP_BACKUP_INTERVALL=12
 | | 
 DEBUG | This will activate debug printouts in adapted containers | DEBUG=0

## Container names
The container names will be automatically generated, based on the parent directory name and the names given in the ``` docker-compose.yml ``` file
