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