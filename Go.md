Instalación

    $ cd
    $ curl -O https://storage.googleapis.com/golang/go1.6.linux-amd64.tar.gz
    $ tar xvf go1.6.linux-amd64.tar.gz
    $ sudo chown -R root:root ./go
    $ sudo mv go /usr/local
    $ sudo pluma ~/.profile
    export GOPATH=$HOME/Documentos/go
    export PATH=/usr/local/go/bin:$PATH:$GOPATH/bin
    $ source ~/.profile

Fuentes:
  
  + https://www.digitalocean.com/community/tutorials/how-to-install-go-1-6-on-ubuntu-16-04
  + http://stackoverflow.com/questions/21001387/how-do-i-set-the-gopath-environment-variable-on-ubuntu-what-file-must-i-edit
  + http://www.hostingadvice.com/how-to/install-golang-on-ubuntu/
