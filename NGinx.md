# TUTORIAL NGinx

#### Instalación de NGinx

Ingresar el siguiente código en la consola.

    $ sudo apt-get update
    $ sudo apt-get install nginx
    
#### Cambiar Puerto de NGinx

Ingresar el siguiente código en la consola.

    $ sudo nano /etc/nginx/sites-enabled/default
    Cambiar : server { listen 81; }

Luego reiniciamos el servidor:
    
    $ sudo service nginx restart

Crear un nuevo 'block' (equivalente a vhost en apache2):

1. Crear una carpeta dónde estarán los archivos del servidor

2. Darle a ese directorio los permisos adecuados:
	
	  $ sudo chmod -R 755 /home/pepe/Documentos/nginx2

3. Crear el archivo de configuración del nuevo block:

	  $ sudo cp /etc/nginx/sites-available/default /etc/nginx/sites-available/block2.com

4. Editar el puerto y el directorio del nuevo bloque:

	  $ sudo pluma /etc/nginx/sites-available/block2.com

5. Habilitar el nuevo bloque:

	  $ sudo ln -s /etc/nginx/sites-available/block2.com /etc/nginx/sites-enabled/

6. Reiniciar el Servidor:

	  $ sudo service nginx restart

#### HTTPS

Verificar firewall:

    $ sudo ufw app list

Crear certificado SSL

    $ sudo openssl req -x509 -nodes -days 365 -newkey rsa:2048 -keyout /etc/ssl/private/nginx-selfsigned.key -out /etc/ssl/certs/nginx-selfsigned.crt

    Country Name (2 letter code) [AU]:PE
    State or Province Name (full name) [Some-State]:Lima
    Locality Name (eg, city) []:Lima
    Organization Name (eg, company) [Internet Widgits Pty Ltd]:Software Web Peru
    Organizational Unit Name (eg, section) []:Soporte
    Common Name (e.g. server FQDN or YOUR name) []:SWP
    Email Address []:jvaldiva@softweb.pe

    $ sudo openssl dhparam -out /etc/ssl/certs/dhparam.pem 2048

Configurar NGnix para usar SSL, editando el archivo '/etc/nginx/snippets/ssl-params.conf':

    # from https://cipherli.st/
    # and https://raymii.org/s/tutorials/Strong_SSL_Security_On_nginx.html

    ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
    ssl_prefer_server_ciphers on;
    ssl_ciphers "EECDH+AESGCM:EDH+AESGCM:AES256+EECDH:AES256+EDH";
    ssl_ecdh_curve secp384r1;
    ssl_session_cache shared:SSL:10m;
    ssl_session_tickets off;
    ssl_stapling on;
    ssl_stapling_verify on;
    resolver 8.8.8.8 8.8.4.4 valid=300s;
    resolver_timeout 5s;
    # Disable preloading HSTS for now.  You can use the commented out header line that includes
    # the "preload" directive if you understand the implications.
    #add_header Strict-Transport-Security "max-age=63072000; includeSubdomains; preload";
    add_header Strict-Transport-Security "max-age=63072000; includeSubdomains";
    add_header X-Frame-Options DENY;
    add_header X-Content-Type-Options nosniff;

    ssl_dhparam /etc/ssl/certs/dhparam.pem;

Crear un backup del block de nginx:

    $ sudo cp /etc/nginx/sites-available/default /etc/nginx/sites-available/default.bak

Editar '/etc/nginx/sites-available/default'

    upstream backend  {
      server 0.0.0.0:8888;
      server 0.0.0.0:8889;
    }

    server {
      listen 80 default_server;
      listen [::]:80 default_server;
      server_name 192.168.1.4;
      
      listen 443 ssl;
      ssl_certificate /etc/ssl/certs/nginx-selfsigned.crt;
      ssl_certificate_key /etc/ssl/private/nginx-selfsigned.key;

      client_max_body_size 50M;

      #access_log  /var/www/Ret/Returner/logs/nginx.access.log;
      #error_log  /var/www/Ret/Returner/logs/nginx.error.log;

      location = /home/pepe/Documentos/python/flask/static/assets/img/favicon.ico { access_log off; log_not_found off; }
      location /static/ {
          root /home/pepe/Documentos/python/flask/static/;
      }

      # Reverse Proxy
      location / {
        proxy_pass  http://backend;
      }

      return 301 https://$server_name;
    }

#### Balanceador de carga

Editar '/etc/nginx/sites-available/default'

    upstream backend1 {
      server 0.0.0.0:8888 weight=1;
      server 0.0.0.0:8889 weight=2;
    }

    server {
      listen 90;

      location / {
        proxy_pass http://backend1;
      }
    }

Reiniciar servicio


---

Fuentes:

+ https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-16-04
+ https://stackoverflow.com/questions/41853534/install-ssl-certificate-on-nginx-ubuntu-16-04-x64-digital-ocean
+ https://www.booleanworld.com/configure-nginx-load-balancer/
