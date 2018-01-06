## RethinkDB

Instlación de software:

    $ source /etc/lsb-release && echo "deb http://download.rethinkdb.com/apt $DISTRIB_CODENAME main" | sudo tee /etc/apt/sources.list.d/rethinkdb.list
    $ wget -qO- https://download.rethinkdb.com/apt/pubkey.gpg | sudo apt-key add -
    $ sudo apt-get update
    $ sudo apt-get install rethinkdbsudo apt-get update
    
Arrancar el servidor y el cliente web:    
    
    $ rethinkdb
    
Una vez arrancado el servidor, se puede acceder al cliente web con la siguiente url:

    http://localhost:8080/

---

Fuentes:

+ https://www.rethinkdb.com/docs/install/ubuntu/
+ https://www.rethinkdb.com/docs/start-a-server/