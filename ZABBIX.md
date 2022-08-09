sudo docker run --name zabbix-server-pgsql -e DB_SERVER_HOST="172.17.0.2" -e POSTGRES_USER="aivorra" -e POSTGRES_PASSWORD="Swf522nn" -d zabbix/zabbix-server-pgsql:alpine-5.0-latest

sudo docker exec -ti zabbix-server-pgsql /bin/bash

sudo docker logs zabbix-server-pgsql

--

sudo docker run --name zabbix-web-apache-pgsql -e DB_SERVER_HOST="172.17.0.2" -e POSTGRES_USER="aivorra" -e POSTGRES_PASSWORD="Swf522nn" -e ZBX_SERVER_HOST="zabbix-server" -e PHP_TZ="America/Argentina/Mendoza" -d zabbix/zabbix-web-apache-pgsql:alpine-5.0-latest


sudo docker run --name zabbix-server-pgsql -e DB_SERVER_HOST="172.17.0.2" -e POSTGRES_USER="aivorra" -e POSTGRES_PASSWORD="Swf522nn" -d zabbix/zabbix-server-pgsql:ubuntu-5.0-latest

sudo docker run --name zabbix-web-apache-pgsql -e DB_SERVER_HOST="172.17.0.2" -e POSTGRES_USER="aivorra" -e POSTGRES_PASSWORD="Swf522nn" -e ZBX_SERVER_HOST="zabbix-server" -e PHP_TZ="America/Argentina/Mendoza" -d zabbix/zabbix-web-apache-pgsql:ubuntu-5.0-latest