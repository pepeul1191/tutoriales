# INSTALACIÓN LUMEN

#### 1) Instalar composer
$ sudo apt-get update <br>
$ sudo apt-get install curl php5-cli git <br>
$ curl -sS https://getcomposer.org/installer | sudo php -- --install-dir=/usr/local/bin --filename=composer

#### 2) Instalar guzzlehttp de composer
$ sudo composer global require guzzlehttp/guzzle 5.2.0

#### 3) Instalar lumen
$ sudo composer global require "laravel/lumen-installer=~1.0"

#### 4) Crear proyecto lumen
$ lumen new micro-lumen

#### 5) Configurar el host

$ sudo gedit /etc/hosts

127.0.0.1	localhost <br>
127.0.1.1	pepe-HP-Pavilion-11-x360-PC <br>
127.0.0.1	lumen-app.com <br>

$ sudo cp /etc/apache2/sites-available/000-default.conf  /etc/apache2/sites-available/micro-lumen.com.conf
$ sudo gedit /etc/apache2/sites-available/micro-lumen.com.conf

+ DocumentRoot /home/pepe/www/micro/public
+ ServerName micro-lumen.com
+ ServerAlias www.micro-lumen.com

$ sudo a2ensite micro-lumen.com.conf
$ sudo service apache2 restart


Fuentes: <br>
https://www.digitalocean.com/community/tutorials/how-to-install-and-use-composer-on-ubuntu-14-04 <br>
https://github.com/guzzle/guzzle/issues/982 <br>
http://lumen.laravel.com/docs/installation <br>
https://www.youtube.com/watch?v=PaEs4-3Rrok <br>
https://www.youtube.com/watch?v=0gJ5QxvdWSo <br>