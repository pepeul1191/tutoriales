# Uso Stomp-PHP

#### 1) Instlar Apache2

$ sudo apt-get install apache2

#### 2) Instlar PHP5

$ sudo apt-get install apache2 php5 libapache2-mod-php5 <br>
$ sudo apt-get install php5-mysql php5-curl php5-gd php5-intl php-pear php5-imagick php5-imap php5-mcrypt php5-memcache php5-ming php5-ps php5-pspell php5-recode php5-snmp php5-sqlite php5-tidy php5-xmlrpc php5-xsl <br>
$ sudo apt-get install php5-xcache && sudo apt-get install php5-xdebug

#### 3) Instalar Stomp

$ sudo apt-get install tasksel  <br>
$ sudo apt-get install php-pear  <br>
$ sudo apt-get install php5-dev  <br>
$ sudo pecl install stomp-1.0.8  <br>
Añadir extension=stomp.so a la archivo /etc/php5/cli/php.ini <br>
Añadir extension=stomp.so a la archivo /etc/php5/apache2/php.ini <br>
$ sudo service apache2 restart  <br>

Comprobar instalación de Stomp con PHP creando un archivo php con lo siguiente:

` <?php phpinfo(); ?> `

#### 3) Modificar el Archivo de Configuración de ActiveMQ

Buscamos en la carpeta donde tenemos descomprimido ActiveMQ, entramos a la subcarpeta 'conf' y editamos el archivo 'activemq.xml' con lo siguiente <br>

`<transportConnector name="stomp" uri="stomp://0.0.0.0:61613?maximumConnections=1000&amp;wireFormat.maxFrameSize=104857600??trace=true"/>`

#### Fuentes

* http://techstuff.leighonline.net/clarification-through-obfuscation-news/installingactivemqstompandlamponubuntu <br>
* https://www.howtoforge.com/ubuntu-lamp-server-with-apache2-php5-mysql-on-14.04-lts <br>