# Instalación SSDB

---

Cambiamos a la carpeta dónde vamos a instalar la base de datos.

    $ sudo mkdir /usr/local/ssdb 
    $ cd /usr/local/ssdb

Descargamos la base de datos:

    $ sudo wget --no-check-certificate https://github.com/ideawu/ssdb/archive/master.zip

Instalamos la base de datos:

    $ sudo unzip master
    $ cd ssdb-master
    $ sudo make
    $ sudo make install
    
Iniciar y Parar ssdb-server

    # start master
    ./ssdb-server ssdb.conf

    # or start as daemon
    ./ssdb-server -d ssdb.conf

    # stop ssdb-server
    ./ssdb-server ssdb.conf -s stop

    # restart
    ./ssdb-server ssdb.conf -s restart

Cliente por la terminal

    $ gem install ssdb
    $ irb
    irb(main) : > require "ssdb"
    irb(main) : > ssdb = SSDB.new url: "ssdb://127.0.0.1:8888"
    irb(main) : > ssdb.get("mykey")

---

#### Fuente

+ http://ssdb.io/docs/install.html
+ https://github.com/bsm/ssdb-rb