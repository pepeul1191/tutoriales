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