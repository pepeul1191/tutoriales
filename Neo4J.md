# Neo4J
---

Instalación en Ubuntu 16.04

    $ wget --no-check-certificate -O - https://debian.neo4j.org/neotechnology.gpg.key | sudo apt-key add -
    $ echo 'deb http://debian.neo4j.org/repo stable/' | sudo tee /etc/apt/sources.list.d/neo4j.list
    $ sudo apt update
    $ sudo apt install neo4j
    
Parar el servidor:

    $ sudo service neo4j stop

Arrancar el servidor:

    $ sudo service neo4j start
    
Accesando a Neo4j:

    http://localhost:7474/browser/.

I had some problems logging in with the default username and password (neo4j and neo4j), but this was easily resolved by deleting the file /var/lib/neo4j/data/dbms/auth and restarting the server.

---

#### Fuente : 

+ http://www.exegetic.biz/blog/2016/09/installing-neo4j-ubuntu-16-04/