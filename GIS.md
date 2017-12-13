## GIS

#### QGIS

Para instalar QGIS en Ubuntu 16.04 añadir las siguientes lineas en '/etc/apt/sources.list' :

    deb http://qgis.org/debian xenial main
    deb-src http://qgis.org/debian xenial main

Despues ejecutar el siguiente codigo en consola:

    $ sudo apt-get update
    $ sudo apt-get install qgis python-qgis qgis-plugin-grass
    
#### Spatialite

Spatialite es una extension en SQLite para que este motor de base de datos pueda manejar SQL Geoespacial. Para instalar su cliente grafico es con el siguiente codigo:

    $ sudo apt-get install spatialite

#### Conceptos

Existen 3 tipos de elementos

1. Point, que es una cordenada x,y
2. LineString, que es un segmento que conecta dos puntos.
3. Polygon, es un conjunto de lineas contiguas, que ademas puede tener un segmento vacio dentro.

#### Sitios Web de Descargas de Shapes

+ http://www.diva-gis.org/datadown

--- 

Fuentes

+ https://gis.stackexchange.com/questions/191681/install-qgis-2-14-essen-on-ubuntu-16-04-xenial
+ https://apps.ubuntu.com/cat/applications/quantal/spatialite-gui/
+ http://daniel-azuma.com/articles/georails/part-3