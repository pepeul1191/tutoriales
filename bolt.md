# Bold CMS - PHP

Instalación por composer

    $ composer create-project bolt/composer-install:^3.5 <MYPROJECT> --prefer-dist
    $ cd <MYPROJECT>
    $ composer run-script post-create-project-cmd

Instalación de librerías de PHP

    $ sudo apt-get install php-intl php-zip php-fpm php-xdebug

Configurar '/etc/php/7.0/mods-available/xdebug.ini' agregando la siguiente línea:

    xdebug.max_nesting_level=500

Reinicar PHP:

    $ /etc/init.d/php7.0-fpm restart

Modificar estructura webroot - Fuente 3 Option 6: Move the files outside of the public folder haciendo:

1. Mover el contenido de la carpeta public a root_path

2. Archivo .bolt.yml

    extensions:
        - Bundle\Site\CustomisationExtension

    paths:
        cache: app/cache
        config: app/config
        database: app/database
        web: .
        themebase: theme
        files: files
        view: bolt-public/
        
3. Archivo index.php

    $app = require dirname(__FILE__) . '/vendor/bolt/bolt/app/web.php';
    
Ejecutar build on server:

    $ php -S localhost:8080

### Crear extensiones:

    $ composer create-project --no-install bolt/bolt-extension-starter:^3.0 <newextname>

---

Fuentes:

+ https://askubuntu.com/questions/516161/location-to-edit-xdebug-max-nesting-level-in-ubuntu-14-04-php-using-lighttpd
+ https://www.cyberciti.biz/faq/unix-linux-restart-php-service-command/
+ https://docs.bolt.cm/3.1/howto/troubleshooting-outside-webroot