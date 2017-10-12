Configuracion de Ansible y los Playbooks
---
Se han creado 3 roles principales segun lo requerimientos pedidos por MediaWiki, los cuales son:

1. Apache
2. MySQL
3. MediaWiki


Ejecutar rol Apache 
--------

Para la ejecución del rol apache se utiliza el siguiente comando
```
$ ansible-playbook -i hosts Apache.yml
```

Ejecutar rol MySQL 
--------
Para la ejecución del rol MySQL se utiliza el siguiente comando
```
$ ansible-playbook -i hosts Mysql.yml
```

Ejecutar rol MediaWiki 
---------
Para la ejecución del rol apache se utiliza el siguiente comandos

```
$ ansible-playbook -i hosts MediaWiki.yml
```
Una vez hecho esto, puede comprobar los resultados consultando http://localhost/media y se pueden ver los resultados de MediaWiki
