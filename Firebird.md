# Firebird

## Instalacion

    $ sudo apt-get install firebird2.5-super
    
Usuario por defecto: SYSDBA
Contraseña facil: 123

Arrancar servicio:

    $ dpkg-reconfigure firebird2.5-super
    
Crear usuario firebird:

    $ sudo adduser `id -un` firebird
    
Cambiar el usuario propietario de carpeta donde estara la base de datos:

    $ sudo chown -R firebird:firebird <<ruta_carpeta>>

## Clientes de la Base de Datos

El cliente grafico es FlameRobin:

    $ sudo apt-get install flamerobin
    
Cliente por linea de comando:

    $ isql-fb
    
Crear base de datos:

    > CREATE DATABASE "localhost:/home/pepe/Documentos/perl/Gestion-App/db/gestion" USER "SYSDBA" password "123";

Conectarse a base de datos:

    > CONNECT "localhost:/home/pepe/Documentos/perl/Gestion-App/db/gestion" USER "SYSDBA" password "123";
    
--- 

Fuentes:

+ https://firebirdsql.org/manual/ubusetup.html
+ https://quilate.atlassian.net/wiki/spaces/QP/pages/19825072/Instalar+Firebird+2.5+en+Linux
+ https://askubuntu.com/questions/945327/how-to-installing-firebird-on-ubuntu-16-04