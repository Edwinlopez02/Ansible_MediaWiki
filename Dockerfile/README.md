 Configuracion de host docker 
------------------------
Se configuran los hosts de las imagenes que se van a crear.

 Creación del docker 
------------------------
-Primer paso
Creación de la imagen en la que se basará el contenedor.

Se ejecuta el siguiente comando para la realización del pasos

```
docker build -t server .
```
Y tenemos creado nuestra imagen con ubuntu y ssh activo.
-Segundo paso 

```
Nombre del contenedor main = server_main

$ docker run -d -P --name wiki_main -p 2221:22 -p 80:80 wiki_host

Nombre del contenedor mysql = wiki_db

$ docker run -d -P --name wiki_db -p 2222:22 -p 3306:3306 wiki_host

```
Los nombre de los alias que tienen los contenedores
 ---
```
wiki_main 
 wiki_db 
```
-Tercer Paso

Registramos los alias de la siguiente manera:

` $ echo "127.0.0.1 wiki_main wiki_db" | sudo tee -a /etc/hosts `

Y con esto contamos con los contenedores creados y con posibilidad de identificación.

-Cuarto paso
Realiza una prueba de conexión a las maquinas que se crearon recientemente, por defecto el paso anterior crea n cantidad de dockers con el
```
$ ssh root@wiki_main -p 2221 -i ../key

$ ssh root@wiki_db -p 2222 -i ../key
```


