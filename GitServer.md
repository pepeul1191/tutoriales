# Git Server

## Cofinguracion Inicial

TODO

## Crear Repositorio Git

Instalar Git y GitCore:

    $ sudo apt-get install git git-core
    
Crear usuario 'git':

    $ sudo adduser 'git'

En el servidor, loguearse con el usuario 'git':

    $ su git
    
Crear carpta para almacenar llaves:

    $ mkdir .ssh && chmod 700 .ssh
    $ touch .ssh/authorized_keys && chmod 600 .ssh/authorized_keys
    
## Crear Proyecto Git
    
Una vez logueado ir a la carpeta donde estan los repositorios y crear una carpeta que termine en punto git:

    $ mkdir <proyecto>.git

Entrar en la carpeta:

    $ cd <proyecto>.git
    
E inicializar un proyecto git:

    $ git init --bare
    
## Pushear Proyecto a Repositorio Creado

Crear clave ssh para permitir la comunicacion entre el cliente y servidor Git, primero hay que crear una carpta llamada '.ssh' en la raiz del directorio del servidor en el cliente git:

    $ mkdir .ssh
    
Cambiar los permisos en el directorio creado:

    $ chmod 0700 $HOME/.ssh
    
Entrar en el directorio creado:

    $ cd .ssh

Crear llave ssh

    $ ssh-keygen -t rsa
    
Se crearan dos archivos:

    $HOME/.ssh/id_rsa– contains your private key.
    $HOME/.ssh/id_rsa.pub – contain your public key.
    
En el servidor hay que crear el usuario que usara un reposotirio:

    $ sudo adduser 'nombre_usuario'

Subir el archivo 'id_rsa.pub' al servidor git renombrando previamente el archivo antes de subir, e ingresar el siguiente codigo en el servidor git:

    $ cat /tmp/id_rsa.pub >> /.ssh/authorized_keys

Setear como origin el repositorio recien creado:

    $ git remote set-url origin nombre_usuario@<ip-servidor-git>:<ruta-directorio-repositorio-git-creado>
    
Clonar proyecto git:

    $ git clone git@<ip-servidor-git>:<ruta-directorio-repositorio-git-creado>

--- 

Fuentes:

+ https://git-scm.com/book/en/v2/Git-on-the-Server-Setting-Up-the-Server
+ https://help.github.com/articles/changing-a-remote-s-url/
+ http://www.cyberciti.biz/faq/how-to-set-up-ssh-keys-on-linux-unix/
+ https://www.youtube.com/watch?v=r93gUZbjWEo