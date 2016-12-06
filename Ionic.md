 # Ionic
  ---

 1) Instalar Ionic <br>

Los requisitos es tener instalado Git, Node JS (v0.12.2) y Node Package Manager(2.10.0). Luego de tener esto instalado, tenemos que instalador los siguientes paquetes de npm de manera global:

    $ sudo npm install –g bower
    $ sudo npm install -g gulp
    $ sudo npm install -g cordova
    $ sudo npm install -g ionic
    $ sudo npm install -g yo
    $ sudo npm install –g grunt 
    $ sudo npm install –g grunt-cli
    $ sudo npm install –g generator-ionic

 2) Crear el scaffolding proyecto Ionic <br>

    $ yo ionic {nombre_proyecto}
    o
    $  ionic start ionic-maps blank --v2 

 3) Arrancar el servidor de grunt <br>

 Dentro del directorio donde hemos elaborado el scaffolding escribir el siguiente código:

    $ grunt serve
    
Nota: En caso de error "Waiting…Fatal error: watch ENOSPC" usar el siguiente código y volver a ejecutar $ grunt serve

    $ echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf && sudo sysctl -p

 ## Fuentes
 ---

 + https://nodesource.com/blog/nodejs-v012-iojs-and-the-nodesource-linux-repositories/#installing-node-js-v0-12serv
 + http://stackoverflow.com/questions/16748737/grunt-watch-error-waiting-fatal-error-watch-enospc