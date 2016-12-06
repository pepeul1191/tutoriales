# MongoDB

---

#### Instalación de MongoDB

Importar la llave pública:

    $ sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
    
Crear lista de archivos para MongoDB:

    $ echo "deb http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list
    
Actualizar la lista de paquetes:

    $ sudo apt-get update
    
Instalar MongoDB

    $ sudo apt-get install -y mongodb-org
    
Arrancar el servicio de MongoDB
    
    $ sudo service mongod start

#### Intalación de Librería con Python

En línea de comandos ingresar lo siguiente:

    $ sudo pip install pymongo
    
#### Comandos

Comenzar a usar MongoDB:
    
    $ mongo

Ver bases de datos disponibles:

    > show dbs

Escoger la base de datos usar (en caso de no existir se creará siempre y cuando se cree alguna colección despues):

    > use db_accessos
    
Borrar colección:

    > db.estado_usuario.drop()
    
Ver colecciones:

    > show colecctions
    
Insertar un documento:

    > document = ({"usuario" : "admin", "contrasena": "QJOPfBjSrktR5f4aZKOaGpdZs8fnwzYAoT3F2dOrIks=", "codigo_activacion": "", "estado" : "activo", "tipo": "empleado"} )
    > db.usuarios.insert(document)

Ver el contenido de una determinada colección:
    
    > db.usuario.find()
    
Ver el contenido de una determinada colección con un mejor formato:

    > db.usuarios.find().pretty()
    
Insertar múltiples documentos en usa sola consulta:

    > db.estado_usuarios.insert([{"estado" : "Activo"}, {"estado":"Activación Pendiente"}, {"estado": "Suspendido"}, {"estado":"Eliminado"},{ "estado":"No Creado"}] )
    
Borrar documento:
    > db.products.remove( { qty: { $gt: 20 } }
    > db.permisos.remove({_id:ObjectId("56d8c116ef627524938da3b0")})

Actualizar un documento:
    > db.roles.update({"rol":"SuperAdministrado"}, {"rol":"SuperoAdministrador"})
    
Para realizar un backup de un base de datos incluyendo los stored functions.

    $ mongodump --db <nombre de db> --out <ruta donde se guardará el backup>
    
Para restaurar

    $ mongorestore -d [your_db_name] [your_dump_dir]

---

#### Fuente : 

+ http://manpages.ubuntu.com/manpages/wily/man1/yui-compressor.1.html
+ https://docs.mongodb.org/getting-started/python/client/
+ https://docs.mongodb.org/manual/reference/method/db.collection.update/
+ https://docs.mongodb.com/manual/tutorial/backup-and-restore-tools/