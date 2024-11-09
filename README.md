# repositoriop5

Configura un contenedor coa imaxe oficial de bind9 usando docker-compose.

En el archivo docker-compose.yml configuramos  el  contenedor de BIND9 para que  funcione como un servidor DNS


version: '3'
services:
  bind9:
    image: internetsystemsconsortium/bind9:9.18
    container_name: bind9-adri
    ports:
      - 54:53/tcp
      - 54:53/udp
      - 127.0.0.1:953:953/tcp
    restart: always
    volumes:
     - ./etc_bind:/etc/bind
     - ./cache_bind:/var/cache/bind
     - ./lib_bind:/var/lib/bind
     - ./log_bind:/var/log




Explicación opciones:
El apartado version indica la version del docker compose que es la  versión 3, services se define como los  servicios que se van a ejecutar en los contenedores, bind9 es el nombre del servicio que estoy creando, container_name: bind9-adri  se le añade este nombre al contenedor, ports  se emplea para definir los puertos para que el contenedor sea accesible desde afuera, restart sirve para que se reinicie automaticamente en caso de que falle  el contenedor y los volumes que permiten montar directorios o archivos del host en el contenedor para crear los volumes hice un mkdir,  
