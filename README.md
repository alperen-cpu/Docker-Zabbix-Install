# Docker-Zabbix-Install

![image](https://user-images.githubusercontent.com/85456369/207133203-29794065-1dfe-4461-a38f-f3fc74528bef.png)

Welcome to this guide on how to run Zabbix Server 6.0 LTS in Docker Containers. Zabbix is a free and open-source, robust enterprise-grade tool used to monitor and analyze the performance of components. Zabbix offers real-time monitoring of networks, identifies faults as soon as they occur, and sends alerts to the response team. This helps to ensure business continuity


# Used Technologies

- Debian 11 Bullseye slim
- Nginx
- PostgreSQL

After the image is created, you need to run the .sql file in the container.

  ```
  zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | psql -U ${POSTGRES_USER} -d ${POSTGRES_DB}
  ```
 Dasboard Zabbix-Server is not running
 
```sed -i 's/DBName=zabbix/DBName='${POSTGRES_DB}'/g' /etc/zabbix/zabbix_server.conf```<br>
```sed -i 's/DBUser=zabbix/DBUser='${POSTGRES_USER}'/g' /etc/zabbix/zabbix_server.conf```<br>
```sed -i 's/# DBPassword=/DBPassword='${POSTGRES_PASSWORD}'/g' /etc/zabbix/zabbix_server.conf```

## Environment Variables

To run this project you will need to add the following environment variables to your .env file

`POSTGRES_PASSWORD=`
`POSTGRES_DB=`
`POSTGRES_USER=`




  
## Server Run

project clone

```bash
  git clone https://github.com/alperen-cpu/Docker-Zabbix-Install.git
```

project directory go

```bash
  cd Docker-Zabbix-Install
```

docker-compose.yml edit
```
image: "test-zabbix"
```

After
```bash
  docker build -t image-name .
```

Server run

```bash
  docker compose up -d
```

  
