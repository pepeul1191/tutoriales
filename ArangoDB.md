## ArangoDB

Instlación de ArangoDB:

    $ wget https://www.arangodb.com/repositories/arangodb3/xUbuntu_16.04/Release.key
    $ sudo apt-key add Release.key
    $ sudo apt-add-repository 'deb https://www.arangodb.com/repositories/arangodb3/xUbuntu_16.04/ /'
    $ sudo apt-get update
    $ sudo apt-get install arangodb3

Revisar el status del servicio instalado:

    $ sudo systemctl status arangodb

Equivalencias AQL con SQL:

| SQL  | AQL |
| ---- |---- |
| SELECT * FROM empresas      | FOR empresa in empresas <br>RETURN empresa |
| DELETE FROM empresas      | FOR empresa in empresas <br>REMOVE empresa in empresas |
| INSERT INTO locales (nombre) VALUES ('Don Hector')git| INSERT {nombre: 'Don Hector'} IN locales 
| INSERT INTO locales (nombre) VALUES ('Don Hector')<br> + retornado id generado| INSERT {nombre: 'Don Hector'} IN locales LET inserted = NEW <br> RETURN inserted._key

Acceder a ArangoDB con el Shell:

    $ arangosh
    
Acceder a ArangoDB desde el cliente web:

    http://localhost:8529

---

Fuentes:

+ https://devops.profitbricks.com/tutorials/install-and-configure-arangodb-on-ubuntu-1604/
+ https://help.github.com/articles/organizing-information-with-tables/
+ https://docs.arangodb.com/3.1/AQL/DataQueries.html
+ https://docs.arangodb.com/2.8/WebInterfaces/