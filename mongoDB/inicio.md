## Proceso de instalacion de mongo DB en el sistema operativo Ubuntu:

1. Actualizar el sistema:
_$ sudo apt update_

2. Instalar mongo DB con la opcion prefijada a yes:
_$ sudo apt install -y mongodb;_

Con esto onstala algunos paquetes y el servidor de mongo inicia automaticamente,

Comandos para configurar el servidor de la base de datos:

1. Comprobar el estado del servidor:
_$ sudo systemctl status mongodb_

2. Conexion con la base de datos MongoDB y ejecucion de un diagnostico:
_$ mongo_ Con este comando inicias la shell

El output de este comando escupe la version de la base de datos, la direccion host y puerto del servidor, y el por ultimo el estado del servidor.

Para parar el servidor de MongoDB se puede manejar mediante el comando:
_$ sudo systemctl stop mongodb_

Para arrancar de nuevo el servidor de mongo se usa:
_$ sudo systemctl start mongodb_

Tambien es posible resetear el servidor de mongodb con el comando:
_$ sudo systemctl restart mongodb_

### Por defecto el servidor de mongo tiende a iniciarse con el arranque del sistema, pero esta opcion se puede configurar:
_$ sudo systemctl disable mongodb_

Y para arrancarlo de nuevo con la opcion automatica de inicio:
_$ sudo systemctl enable mongodb


### Para permitir que otros dispositivos se conecten con el servidor de mongo se tiene que configurar el sistema para que permita conexiones en el puerto 27017:
_$sudo ufw allow from your others server ip/32 to any port 27017_

#### Para ver el trafico de datos en el puerto 27017 se puede ejecutar el comando:
_$ sudo ufw status_


#### Comandos basicos para manejar la base de datos MongoDB:

1. Mostrar las bases de datos activas en mongodb:
_$ show dbs;_

2. Usar la base de datos de la lista:
_$ use [database name]_

3. Introducir datos en la base de datos que estas usando:
_$ db.[coleccion].insert(   [documento en formato JSON]  ) ;_

4. Listar las colecciones de una base de datos:
_$ show collections;_

5. Search something in the collections table:
_$ db.[collection].find().pretty();_

6. Se pueden eliminar documentos de una collecion mediante el comando:
_$ db.[collection name].remove({id});_

7. Se pueden tambien introducir documentos con un _id_ personalizado por el usuario, ya que hasta ahora los comandos de introducir datos se hacia mediante el comando _$db.[collection name].insert({JSON Document Format})_, y el id se generaba automaticamente. 
_$ db.[collection name].insert({_id: 1, name: "test message"});_

8. Para actualizar o modificar un documento se usa el comando _update_ donde recibe dos parametros, uno es el campo _where_, es decir, el filtro que usa para encontrar el documento, y el segundo parametro es el campo que hay que actualizar/modificar:
_$ db.[collection].update({where condition to find to document to update}, {set the json all document with the updated field});_