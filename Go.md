Instalación

    $ cd
    # amd64
    $ wget https://dl.google.com/go/go1.9.4.linux-amd64.tar.gz
    # arm
    $ wget https://storage.googleapis.com/golang/go1.9.linux-armv6l.tar.gz
    $ sudo tar -xvf go1.9.4.linux-amd64.tar.gz
    $ sudo chown -R root:root ./go
    $ sudo mv go /usr/local
    $ sudo pluma ~/.profile
    export GOPATH=$HOME/Documentos/go
    export PATH=/usr/local/go/bin:$PATH:$GOPATH/bin
    $ source ~/.profile
    
Instalacion de glide (gestor de paquestes)

    $ sudo add-apt-repository ppa:masterminds/glide 
    $ sudo apt-get update 
    $ sudo apt-get install glide
    
Instalacion govendor

    $ go get -u github.com/kardianos/govendor
    $ which govendor
    /home/lrp/go/bin/govendor
    $ govendor init
    $ govendor fetch github.com/jinzhu/gorm
    $ govendor fetch golang.org/x/crypto/bcrypt

Fuentes:
  
+ https://www.digitalocean.com/community/tutorials/how-to-install-go-1-6-on-ubuntu-16-04
+ http://stackoverflow.com/questions/21001387/how-do-i-set-the-gopath-environment-variable-on-ubuntu-what-file-must-i-edit
+ http://www.hostingadvice.com/how-to/install-golang-on-ubuntu/
+ https://tecadmin.net/install-go-on-ubuntu/#
+ https://github.com/Masterminds/glide
+ https://gist.github.com/simoncos/49463a8b781d63b5fb8a3b666e566bb5