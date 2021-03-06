# Instalación de Programas - Ubuntu

Programas en el presente tutorial:

+ Git
+ Ruby
+ Sinatra
+ Atom
+ Sqlite
+ Postgres
+ MongoDB
+ Heroku-Cli

### Git

Git es un sistema de control de version distribuido, para instalar el siguiente programa de debemos actualizar la lista de paquetes de los repositorios:

    $ sudo apt-get update
    
Luego instalamos Git:

    $ sudo apt-get install git

### Ruby
	
Descargamos la lista de paquetes de los repositorios actualizados: para obtener información sobre las versiones más recientes de los paquetes y sus dependencias. 
    
	$ sudo apt-get update
    
Instalamos las dependencias:

    $ sudo apt-get install autoconf bison build-essential libssl-dev libyaml-dev libreadline6-dev zlib1g-dev libncurses5-dev libffi-dev libgdbm3 libgdbm-dev libsqlite3-dev libpq-dev
    
Instalación de 'rbenv':

    $ cd
    $ git clone https://github.com/rbenv/rbenv.git ~/.rbenv
    $ echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
    $ echo 'eval "$(rbenv init -)"' >> ~/.bashrc
    
Refrescamos la las variables de entorno:

    $ source ~/.bashrc
    
Descargamos 'ruby-build':

    $ git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
    
Instalamos Ruby 2.3.1:

    $ rbenv install 2.3.1
    
Configuramos la versión instalada como la versión global para el sistema:

    $ rbenv global 2.3.1
    
Si la instalación de Ruby es correcta, al escribir el comando 'ruby -v' nos debería mostrar un mensaje similar a:

    $ ruby 2.3.1p112 (2016-04-26 revision 54768) [x86_64-linux]
    
Trabajando con las gemas... Para no descargar las documentación de las gemas durante su instalación, usar el siguiente comando:

    $ echo "gem: --no-document" > ~/.gemrc
    
Instalamos la gema 'bundler', el cuál es un gestor de dependencias usados para los proyectos en Ruby:

    $ gem install bundler
    
### Sinatra
	
Para instalar Sinatra, el cuál es un framework web en Ruby, debemos tener instalado Ruby. El comando para instalar Sinatra es el siguiente:
    
	$ gem install sinatra
    
### Atom

Atom es un editor de texto plano que usaremos para programar. Para poder instalar este programa debemos incluir el repositorio de Atom en la lista de repositorios de Ubuntu:

    $ sudo add-apt-repository ppa:webupd8team/atom
    
Actualizamos la lista de paquetes de los repositorios:

    $ sudo apt-get update
    
Instalamos Atom:

    $ sudo apt install atom
    
### SQLite

SQLite es un motor de base auto-contenida, para instalarlo debemos actualizar la lista de paquetes de los repositorios:

    $ sudo apt-get update
    
Luego instalamos SQLite:

    $ sudo apt-get install sqlite3
    
Para poder instalar un cliente gráfico para gestionar esta base de datos, podemos usar el programa SQLiteBrowser, y para instalarlo es mediante el siguiente programa:

    $ sudo apt-get install sqlitebrowser
    
### Postgres

Postgres es un motor de base de datos relacional. Para poder instalar Postgres debemos actualizar la lista de paquetes de los repositorios:

    $ sudo apt-get update

Luego instalamos Postgres:

    $ sudo apt-get install postgresql postgresql-contrib
    
Para poder instalar un cliente gráfico para gestionar esta base de datos, podemos usar el programa PGAdmin3, y para instalarlo es mediante el siguiente programa:

    $ sudo apt-get install pgadmin3
    
### MongoDB

MongoDB es un motor de base de datos no relacional orientada a documentos JSON. Para poder instalar este programa debemos incluir el repositorio de MongoDB en la lista de repositorios de Ubuntu. Si estamos en Ubuntu 17.04, se usaría el siguiente código:
	
    $ sudo apt install mongodb-clients mongodb-server mongodb
    
Si deseamos ingresar al cliente MongoDB mediante consola, podemos usar el siguiente comando:

    $ mongo

Para poder instalar un cliente gráfico para gestionar esta base de datos, podemos usar el programa Robomongo, y para usarlo es necesario descargarlo y descomprimirlo. Para descargar el cliente Robomongo es mediante el siguiente comando:

    $ wget https://download.robomongo.org/1.1.1/linux/robo3t-1.1.1-linux-x86_64-c93c6b0.tar.gz
    
Luego descomprimos el archivo descargado y dentro de la carpeta 'bin' buscamos el archivo 'robomongo' y lo ejecutamos.

### Heroku-CLI

Para conectarse a Heroku de manera remota, necesitamos instalar un cliente, para lo cuál es necesario ingresar el siguiente código:

    $ wget -qO- https://cli-assets.heroku.com/install-ubuntu.sh | sh
    
### Fuentes:

+ https://git-scm.com/
+ https://www.enmimaquinafunciona.com/pregunta/23070/que-significa-sudo-apt-get-update
+ https://www.digitalocean.com/community/tutorials/how-to-install-ruby-on-rails-with-rbenv-on-ubuntu-16-04
+ https://stackoverflow.com/questions/3116015/how-to-install-postgresqls-pg-gem-on-ubuntu
+ https://stackoverflow.com/questions/3458602/sqlite3-ruby-install-error-on-ubuntu
+ http://bundler.io/
+ http://www.sinatrarb.com/intro.html
+ http://tipsonubuntu.com/2016/08/05/install-atom-text-editor-ubuntu-16-04/
+ https://www.sqlite.org/
+ https://www.linuxhint.com/install-sqlite-browser-ubuntu/
+ https://www.postgresql.org/
+ https://www.digitalocean.com/community/tutorials/como-instalar-y-utilizar-postgresql-en-ubuntu-16-04-es
+ http://ideafalaz.blogspot.pe/2016/04/instalar-postgresql-y-pgadmin-en-linux.html
+ https://www.mongodb.com/es
+ https://www.digitalocean.com/community/tutorials/como-instalar-mongodb-en-ubuntu-16-04-es
+ https://askubuntu.com/questions/912406/mongo-on-ubuntu-17-04
+ https://robomongo.org/download
+ https://devcenter.heroku.com/articles/heroku-cli#debian-ubuntu

---

 Thanks/Credits

    Pepe Valdivia: developer Software Web Perú [http://softweb.pe], JP ULima [http://ulima.edu.pe]
