## RethinkDB

Instlación de software:

    $ source /etc/lsb-release && echo "deb http://download.rethinkdb.com/apt $DISTRIB_CODENAME main" | sudo tee /etc/apt/sources.list.d/rethinkdb.list
    $ wget -qO- https://download.rethinkdb.com/apt/pubkey.gpg | sudo apt-key add -
    $ sudo apt-get update
    $ sudo apt-get install rethinkdb
    
Arrancar el servidor y el cliente web:    
    
    $ rethinkdb
    
Arrancar el servidor y pero cambiando el puerto del cliente web:

    $ rethinkdb --bind all --http-port 9090
    
Una vez arrancado el servidor, se puede acceder al cliente web con la siguiente url:

    http://localhost:8080/

---

Fuentes:

+ https://www.rethinkdb.com/docs/install/ubuntu/
+ https://www.rethinkdb.com/docs/start-a-server/
+ https://stackoverflow.com/questions/35034890/how-can-i-change-webui-interface-port-8080-for-rethinkdb-on-linux
