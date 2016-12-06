# Servidores - Puertos

### Apache

Para las configuraciones de la ruta de los directorios: <br>

    $ sudo nano /etc/apache2/sites-available/000-default.conf

Para cambiar el puerto del servicio hay que añadir "Listen <puerto>" al final del siguiente archivo: <br>

    $ sudo nano /etc/apache2/apache2.conf

El puerto escogido debe concidir también con el host configurado  en "/etc/apache2/sites-available/000-default.conf"

	ServerAdmin webmaster@localhost
	DocumentRoot /home/pepe/Documentos/apache2

	<Directory /home/pepe/Documentos/apache2 >
			Options Indexes FollowSymLinks MultiViews
			AllowOverride All
			Require all granted
	</Directory>

Para reiniciar el servicio: <br>

    $ sudo service apache2 restart

<b>Puerto (default) : 80, sugerido : 8000</b>

### Lighttpd

Para las configuraciones del servicio (puerto y directorio):

    $ sudo nano /etc/lighttpd/lighttpd.conf

Para reiniciar el servicio: <br>

    $ sudo service lighttpd restart

<b>Puerto (default) : 80, sugerido : 8001</b>

---

        server.modules = (
            "mod_access",
            "mod_alias",
            "mod_compress",
            "mod_redirect",
               "mod_rewrite",
        #	"mod_setenv", #before mod_status, very important!
        #	"mod_status",
        )

        server.modules += ( "mod_setenv" )

        #server.document-root        = "/var/www"
        server.document-root        = "/home/pepe/Programacion/lighttpd"
        server.upload-dirs          = ( "/var/cache/lighttpd/uploads" )
        server.errorlog             = "/var/log/lighttpd/error.log"
        server.pid-file             = "/var/run/lighttpd.pid"
        server.username             = "www-data"
        server.groupname            = "www-data"
        server.port                 = 8001

        #status.status-url = "/server-status",
        setenv.add-response-header =  ( "Access-Control-Allow-Origin" => "http://localhost:3000")

        index-file.names            = ( "index.php", "index.html", "index.lighttpd.html" )
        url.access-deny             = ( "~", ".inc" )
        static-file.exclude-extensions = ( ".php", ".pl", ".fcgi" )

        compress.cache-dir          = "/var/cache/lighttpd/compress/"
        compress.filetype           = ( "application/javascript", "text/css", "text/html", "text/plain" )

        # default listening port for IPv6 falls back to the IPv4 port
        ## Use ipv6 if available
        #include_shell "/usr/share/lighttpd/use-ipv6.pl " + server.port
        include_shell "/usr/share/lighttpd/create-mime.assign.pl"
        include_shell "/usr/share/lighttpd/include-conf-enabled.pl"



---

### NGnix

Para las configuraciones del servicio (puerto y directorio):

    $ sudo nano /etc/nginx/sites-available/default

Para reiniciar el servicio: <br>

    $ sudo service nginx restart

<b>Puerto (default) : 80, sugerido : 8002</b>

---

### MySQL

Para reiniciar el servicio: <br>

    $ sudo service mysql restart

<b>Puerto(default) 3306</b>

### MongoDB

Para reiniciar el servicio: <br>

    $ sudo service mongod restart

<b>Puerto(default) 27019</b>

---

### No arrancar los servicios al encender la máquina

En la línea de comandos usar el siguente código:

    $ sudo echo manual | sudo tee /etc/init/apache2.override && sudo echo manual | sudo tee /etc/init/virtualbox.override && sudo echo manual | sudo tee /etc/init/nginx.override && sudo echo manual | sudo tee /etc/init/lighttp.override && sudo  echo manual | sudo tee /etc/init/mongod.override &&  echo manual | sudo tee /etc/init/mysql.override

---

### Fuentes
+ http://askubuntu.com/questions/291952/how-to-set-a-personalized-port-as-default-in-apache
+ https://www.howtoforge.com/ubuntu-lamp-server-with-apache2-php5-mysql-on-14.04-lts
+ https://www.howtoforge.com/tutorial/installing-lighttpd-with-php-fpm-and-mysql-or-mariadb-on-ubuntu/
+ https://www.howtoforge.com/installing-nginx-with-php5-fpm-and-mysql-on-ubuntu-14.04-lts-lemp
+ http://askubuntu.com/questions/19320/how-to-enable-or-disable-services