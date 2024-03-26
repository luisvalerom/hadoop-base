# Proyecto base de Hadoop

Esto es solo con intención de aprendizaje, no recomendado para producción.

Basado en las imagenes oficiales de [Apache Hadoop]([https://](https://hub.docker.com/r/apache/hadoop))

Se sobreescribio el script entryppoint del *namenode* para habilitar la persistencia de los datos en el cluster.

## Punto de inicio

- Crear la red de trabajo para el cluster en docker: `docker network create hadoop_network`
- Crear los directorios para soportar los volumenes de los distintos servicos del cluster (*namenode*, *datanode*, *timeline*):
  - `mkdir dfs_namenode`
  - `mkdir dfs_data1 dfs_data2 dfs_data3`
  - `mkdir timeline`

## Arrancar el cluster

Para iniciar el cluster utilizamos docker compose:
- `docker compose up -d`

Ya con el cluster en ejecución podemos acceder al *namenode* para por ejemplo lanzar la ejecución de alguna tarea, para esto ejecutamos: `docker exec -it namenode /bin/bash`