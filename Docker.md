## Docker

### Instalacion:

Descargar

    $ sudo apt-get update
    $ sudo apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
    $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    $ sudo apt-key fingerprint 0EBFCD88
    $ sudo add-apt-repository \
       "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
       $(lsb_release -cs) \
       stable"
    $ sudo apt-get update
    $ sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose

Instalar una versión específica de docker:

    $ apt-cache madison docker-ce docker-ce-cli # ver versiones
    $ sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io

Agregar usuario a grupo:

    $ sudo usermod -aG docker $USER
    $ newgrp docker

### Comandos

Descargar imagen:

    $ docker pull <repo>

Ver imágenes descargadas:

    $ docker image ls

Ejecutar imagen:

    $ docker run <repo>


--

Fuentes:

+ https://docs.docker.com/install/linux/docker-ce/ubuntu/
+ https://stackoverflow.com/questions/48568172/docker-sock-permission-denied
+ https://docs.docker.com/get-started/
