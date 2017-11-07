Configuracion de Ansible y los Playbooks
---
Se han creado 3 roles principales segun lo requerimientos pedidos por MediaWiki, los cuales son:

1. Apache
2. MySQL
3. MediaWiki

Paso 1: instalación de los servidores web y de archivos
------------------------
Instalamos el servidor web en el wiki_web_server

``ansible-playbook -i ../hosts webserver.yml``

Paso 2: instalación del servidor Mysql.
-------------------------

Intalamos el servidor mysql en el wiki_mysql_server

``ansible-playbook -i ../hosts sqlserver.yml``

Este comando nos ayudará a verificar si la conexion fue correcta :

``ssh root@server02 -p 2222 -i ../key.private``

Luego ejecutamos :

``mysql -h localhost -u root -p``

Donde nos debe mostrar lo siguiente:

  ``mysql> <comandos respectivos>``
  
Luego de realizar esto, podremos hacer lo siguiente.

Paso 3: Instalación de MediaWiki
---------
Instalamos media wiki en el servidor asignado

```
$ ansible-playbook -i hosts MediaWiki.yml
```
Una vez hecho esto, puede comprobar los resultados consultando http://localhost/media y se pueden ver los resultados de MediaWiki
