 # Nginx y PHPMyAdmin
  ---

<b>Requisitos</b>

+ Tener instalado PHP (mínimo php5 php5-fpm php5-mysql)
+ Tener instalado MySQL
+ Tener instalado Nginx
+ No tener instalado PHPMyadmin


1) Instalar los PHP5 y Nginx : <br>

    $ adsfads
    
2) Disminuimos la cantidad de procesadores dedicados a Nginx

    $ sudo nano /etc/nginx/nginx.conf
    
Editamos :

    [...]
    worker_processes 1;
    [...]
    
Reiniciamos el servidor:

    $ sudo service nginx restart
    
3) Configuramos los sitio disponibles de Nginx

    $ sudo nano  /etc/nginx/sites-available/default 
    
    [...]
    server {
    listen 80 default_server;
    listen [::]:80 default_server;
    [...]
    root /var/www/html;
    # Add index.php to the list if you are using PHP
    index index.php index.html index.htm index.nginx-debian.html;
    server_name server.unixmen.local;
    [...]
    
Luego descomentamos la locación de php en el archivo y debe queda como lo siguiente:

     location ~ \.php$ {
    try_files $uri =404;   ---------> Add this line
             #       include snippets/fastcgi-php.conf
    #
    #       # With php5-cgi alone:
    #       fastcgi_pass 127.0.0.1:9000;
    #       # With php5-fpm:
    fastcgi_pass unix:/var/run/php5-fpm.sock;
    fastcgi_index index.php;
    include fastcgi_params;
    }
    
Reiniciamos el servidor:

    $ sudo service nginx restart
    
4) Configurando PHP

Editamos el siguiente archivo:

    $ sudo nano /etc/php5/fpm/php.ini
    
Buscamos la linea que contenga "cgi.fix_pathinfo=1", lo descomentamos  y lo cambios a :
    
    [...]
    cgi.fix_pathinfo=0
    [...]
    
Reiniciamos la funcionalidad fpm de PHP:
    
    $ sudo service php5-fpm restart
    
5) Instalar PHPMyadmin

Usamos el siguiente comando:
    
    $ sudo apt-get install phpmyadmin

Cuando comienze la instalación, seguir los siguientes pasos:

+ No escoger ningun servidor.
+ Dar "Yes" a dbconfig-common

Luego que termine la instalación, debemos crear un enlace de PHPMyadmin en la carpeta donde este la ruta de archivos a ser leidos por el servidor:

    $ sudo ln -s /usr/share/phpmyadmin/ <<ruta>>
    
Y agregamos el siguiente codigo en /etc/nginx/sites-available/default :
    
    location /phpmyadmin {
       index index.php;
    }
    
Reiniciamos el servidor:

    $ sudo service nginx restart

 ## Fuentes
 ---

+ http://www.unixmen.com/how-to-install-lemp-stack-on-ubuntu-15-10/
+ http://stackoverflow.com/questions/26687774/ubuntu-14-nginx-php5-fpm-installed-phpmyadmin-but-403-forbidden-access