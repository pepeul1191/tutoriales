# Mantis Bug Tracker

#### Instalacion en Ubuntu 16.04

Instalacion de Apache Web Server:

    $ sudo apt-get install apache2 libapache2-mod-php -y
    $ sudo systemctl start apache2 
    $ sudo systemctl enable apache2
    
Instalacion de PHP:

    $ sudo apt-get install php php-mysql php-cli php-mbstring -y
    
Editar la zona horaria de PHP-Apache2 en '/etc/php/7.0/apache2/php.ini'
    
    date.timezone = America/Lima
    upload_max_filesize = 50M
    memory_limit = 128M
    
Instalar servidor de base de datos:

    $ sudo apt-get install mysql-server mysql-client -y
    
En el cliente mysql:

    > CREATE USER 'mantis'@'localhost' IDENTIFIED BY 'mantispass123';
    > GRANT ALL PRIVILEGES ON mantis.* TO 'mantis'@'localhost' IDENTIFIED BY 'mantispass123' WITH GRANT OPTION;
    > FLUSH PRIVILEGES;
    
Instalar Mantis BT:

    $ wget https://excellmedia.dl.sourceforge.net/project/mantisbt/mantis-stable/2.4.0/mantisbt-2.4.0.zip
    $ unzip mantisbt-2.4.0.zip
    $ sudo mv mantisbt-2.4.0 /var/www/html/mantis
    $ sudo chown -R www-data:www-data /var/www/html/mantis

En '/etc/apache2/sites-available/mantis.conf' añadiar las siguientes lineas:

    '''
    <VirtualHost *:80>
        ServerAdmin webmaster@yourdomain.com
        DocumentRoot "/var/www/html/mantis"
        ServerName yourdomain.com
        ServerAlias www.yourdomain.com
        ErrorLog "/var/log/apache2/mantis-error_log"
        CustomLog "/var/log/apache2/mantis-access_log" combined
        <Directory "/var/www/html/mantis/">
            DirectoryIndex index.php index.html
            Options FollowSymLinks
            AllowOverride All
            Require all granted
        </Directory>
    </VirtualHost>
    '''
    
    $ sudo a2ensite mantis.conf
    $ sudo systemctl restart apache2
    
Configurar Firewall:

    $ sudo ufw enable
    $ sudo ufw allow 80
    
Acceder a MantisBT por la url 'localhost/mantis' y en usuario de la base de datos colocar el usuario antes creado.

En caso de presentarse un error en la conexion a la base de datos y/o enviar correos SMTP, esta se puede cambiar en el archivo 'config/config_inc.php'. En el caso de la configuracion del tutorial, esta deberia ser:

    '''
    $g_hostname               = 'localhost';
    $g_db_type                = 'mysqli';
    $g_database_name          = 'mantis';
    $g_db_username            = 'mantis';
    $g_db_password            = 'mantispass123';
    $g_phpMailer_method = PHPMAILER_METHOD_SMTP;

    $g_smtp_host = 'smtp.gmail.com:465';
    $g_smtp_username = 'username@gmail.com';
    $g_smtp_password = 'yourpassword';
    $g_smtp_connection_mode = 'ssl';
    $g_smtp_port = 465;
    '''
    
Usuario principal por default : administrator
Contraseña principal por default : root

---

Fuentes:

+ https://hostpresto.com/community/tutorials/how-to-install-and-setup-mantis-bug-tracker-on-ubuntu-16-04/
+ http://php.net/manual/es/timezones.america.php