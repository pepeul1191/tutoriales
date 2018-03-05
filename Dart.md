## Dart

Instalacion de Dart:

    $ sudo apt-get update 
    $ sudo apt-get install apt-transport-https 
    $ sudo sh -c 'curl https://dl-ssl.google.com/linux/linux_signing_key.pub | apt-key add -' 
    $ sudo sh -c 'curl https://storage.googleapis.com/download.dartlang.org/linux/debian/dart_stable.list > /etc/apt/sources.list.d/dart_stable.list' 
    $ sudo apt-get update 
    $ sudo apt-get install dart

Agregar ' export PATH="$PATH:/usr/lib/dart/bin" ' al final del siguiente archivo:

    nano ~/.profile

Refrescar variables:

    $ . ~/.profile

---

Fuentes:

+ https://stackoverflow.com/questions/28466798/how-to-install-pub-command-line-usage-for-dart-on-ubuntu-web-server
+ https://webdev.dartlang.org/angular/tutorial/toh-pt0