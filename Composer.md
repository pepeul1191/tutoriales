# COMPOSER

#### 1) Instalar composer

    $ sudo apt-get update
    $ sudo apt-get install curl php5-cli git
    $ curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer

### 2) Cargar Dependencias

+ En la carpeta donde se quiera tener el proyecto, crear un archivo llamado "composer.json" y dentro del mismo colocar las dependencias.
+ Luego escribir el siguiente comando para crear el composer.phar <br>
    $ curl -sS https://getcomposer.org/installer | php
+ Despues de creado el arhivo .phar, el siguiente código descargará las dependencias. <br>
   php composer.phar install
