# Instalación PHP7 en Ubuntu 16.04
---

Instalación de Apache2, MySQL y SQLite3.

    $ sudo apt-get install apache2 mysql-client mysql-server sqlite3

Instalación de PHP7

    $ sudo apt-get install php libapache2-mod-php php-mcrypt php-mysql php-sqlite3
    
Activar el módulo de reescritura

    $ sudo a2enmod rewrite

Configurar el servidor Apache la habilitación de reescritura

    $ sudo nano /etc/apache2/sites-available/000-default.conf

~~~~    
<VirtualHost *:80>
	ServerAdmin webmaster@localhost
	DocumentRoot /home/pepe/Documentos/php

	<Directory /home/pepe/Documentos/php>
		Options Indexes FollowSymLinks MultiViews
		AllowOverride All
		Require all granted
	</Directory>

	ErrorLog ${APACHE_LOG_DIR}/error.log
	CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>

# vim: syntax=apache ts=4 sw=4 sts=4 sr noet
~~~~

Mostrar los errores producidos por el código PHP cambiando "display_errors = Off" a "On":

    $ sudo nano /etc/php/7.0/apache2/php.ini

Para que los cambios tengan efecto, reiniciar el servidor apache2:

    $ sudo service apache2 restart
    
--- 

Fuentes

+ http://stackoverflow.com/questions/5050426/php-errors-not-being-displayed-in-the-browser-ubuntu-10-10
+ https://www.digitalocean.com/community/tutorials/how-to-install-linux-apache-mysql-php-lamp-stack-on-ubuntu-16-04
+ https://www.dev-metal.com/enable-mod_rewrite-ubuntu-14-04-lts/
