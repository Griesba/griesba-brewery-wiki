Déploiment avec PWD

Avec un exemple tiré du site de docker https://hub.docker.com/_/mysql, on arrive à créer des docker-compose pour chaque base de donnée. Sachant qu'on a 3 base de données

 - db-myql-service
 - db-myql-order
 - db-myql-inventory

# Use root/example as user/password credentials
version: '3.1'

services:

  db:
    image: mysql
    command: --default-authentication-plugin=mysql_native_password
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: s3cret

  adminer:
    image: adminer
    restart: always
    ports:
      - 8080:8080