# TUTORIAL DJANGO

#### Instalación de DJango

Ingresar el siguiente código en la consola.

    $ sudo apt-get update
    $ sudo apt-get install python-django
    $ django-admin --version


#### Creación de un Proyecto Django

Ingresar el siguiente código en la consola.

    $ django-admin startproject projectname
    
#### Arrancar el Servidor de Desarrollo

Dentro del directorio del proyecto, ingresar el siguiente código en la consola.

    $ python manage.py runserver 0.0.0.0:8000
    
#### Sincronización de la Base de Datos

Dentro del directorio del proyecto, ingresar el siguiente código en la consola.

    $ python manage.py syncdb
    
Luego hay que aceptar la creación de un superusuario.

#### Creación del Esqueleto de una Aplicación de Inicio

Dentro del proyecto, ingresar el siguiente código:

    $ python manage.py startapp preguntasyrespuestas
    
#### Creación de Modelos

Dentro del proyecto esqueleto creado debemos agregar modelos los cuales serán mapeados a la base de datos.

    $  python manage.py makemigrations
    $  python manage.py syncdb