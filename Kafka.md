## Apache Kafka

### Instalacion

+ Arrancar servidor:

    $ wget http://www-eu.apache.org/dist/kafka/1.0.0/kafka_2.11-1.0.0.tgz
    $ tar -xzf kafka_2.11-1.0.0.tgz
    $ mv kafka_2.11-1.0.0 kafka
    $ cd kafka
    
Arrancar primero Zookeper    
    
    $ bin/zookeeper-server-start.sh config/zookeeper.properties

Luego arrancar Kafka

    $ bin/kafka-server-start.sh config/server.properties

+ Abrir base de datos:

    ejdb > db.open('mydb');
    
+ Obtener la información de colecciones:

    ejdb> db.getDBMeta();

+ Consultar todos los registros:

    ejdb> db.find('colección');
---

Fuentes:

+ https://kafka.apache.org/quickstart