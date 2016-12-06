# Uso de Ruby On Rails

---

#### Instalación de Ruby On Rails

Previa a esta instalación hay que tener instalado Ruby por medio de Ruby Virtual Enviromnet, como también MySql Server y MySql Client.

    $ sudo gem install rails
    $ rbenv rehash
    $ rails -v
    $ sudo apt-get install mysql-server mysql-client 
    $ sudo gem install mysql2
    $ sudo apt-get install libmysqlclient-dev
    
Adiconalmente devemos tener instalado Javascript runtime con NodeJS para poder usar la funcionalidad de Asset Pipeline.

    $ sudo apt-get install nodejs
    
---

#### Crear Proyecto Rails

Mediante la consola navegar en nuestros directorios.

    $ rails new {nombre_de_proyecto}
    
#### Ejecutar Proyecto Rails

Una vez situada en la carpeta del proyecto de Rails, usar el siguiente código:

    $ rails server
    
En caso de querer usar Puma como servidor, hay que añadir puma en el Gemfile y luego:
    
    $ bundle install
    $  rails s Puma
    
O en caso que se encuentre en un servidor remoto:
    
    $ rails s Puma -p 3001 -b0.0.0.0

#### Creación de un Controlador

Una vez situada en la carpeta del proyecto de Rails, usar el siguiente código:

    $ rails generate controller {nombre_del_controlador} {metodo_1} {metodo_2} ...

---

#### Fuentes

+ https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-ubuntu-14-04
+ http://stackoverflow.com/questions/34384129/mysql2-gem-install-fails-with-unmet-dependencies-libmysqlclient-dev
+ https://github.com/puma/puma