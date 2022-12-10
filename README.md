# Docker

# Descargar Imagenes
~~~Docker
docker pull image-name
~~~

# Detener un contenedor en ejecución
~~~Docker
docker stop container-name
~~~

# Ejecutar Imagen
~~~Docker
docker run image-name
~~~
- ## Ejecutar Imagen en segundo plano
  ~~~Docker
  docler run -d image-name
  ~~~

- ## Ejecutar Imagen con nombre definido
  Al momento de ejecutar cuna imagen al contenedor resultante se le asigna un nombre generico, con la etiqueta **_--name_** se le puede definir un nombre, esto para identificar el contenedor de manera mas facil
  ~~~Docker
  docker run --name container-name image-name
  ~~~

- ## Ejecutar un comando en un contenedor en ejecución
  ~~~Docker
  docker exec -it container-name comand-exec
  ~~~

  - _Example:_ Abrir de forma iterativa la terminal de **_bash_** en el contendor **_postgres_**
    ~~~Docker
    docker exec -it postgres bash
    ~~~
    Para salir

    `Ctrl + D`
# Exponer Puerto
La etiqueta **_-p_** hace publico un puerto d enuestro contenedor, asosiandolo a un puerto de la maquina donde se aloja
~~~Docker
docker run -p num-port-pc:num-port-container image-name
~~~
- _Example:_
  ~~~Docker
  docker run --name docker-psql -e POSTGRES_USER=postgres -e POSTGRES_PASSWORD=postgres -e POSTGRES_DB=postgres -p 5433:5432 -d postgres
  ~~~

# Eliminar una o mas imagenes
~~~Docker
docker rmi container-name
~~~

# Eliminar uno o mas contenedores
~~~Docker
docker rm container-name
~~~

# Listar contenedores en ejecución
~~~Docker
docker ps
~~~
- ## Listar historial de contenedores
  ~~~Docker
  docker ps -a
  ~~~

# Variables de entorno
**_e-_** : Agregar variables de entorno
- Debe ir despues de **_run_**, antes de **_image-name_**.
- Se debe agregar un **_e-_** entre cada variable.
- Consta de 2 partes, **_NAME_VAR_** (_Nombre de la variable_), y, **_value-var_** (Valor de la variable).  
~~~Docker
docker run -e NAME_VAR=value-var image-name
~~~
~~~Docker
docker run -e NAME_VAR_1=value-var-1 -e NAME_VAR_2=value-var-2 image-name
~~~

# Fuentes
- ### [Fuente #1](https://docs.docker.com/engine/reference/commandline/docker/ "Docker documentation")