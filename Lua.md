# TUTORIAL LUA

#### Instalación de Lua5.1

Instalar esta versión ya que es compatible con lapis.

    $ sudo apt-get install lua5.1

#### Instalación de Lapis

Instalar luarocks

    $ sudo apt-get install lua5.1
    $ sudo apt-get install luarocks

Descarga openresty

    http://openresty.org/en/download.html

Instalar openresty

    $ sudo apt-get install nginx libpcre3 libpcre3-dev
    $ tar xvf ngx_openresty-VERSION.tar.gz
    $ cd ngx_openresty-VERSION/
    $ ./configure
    $ make
    $ make install
    
Añadir la variable de entorno de openresty

    $ pluma ~/.bashrc
    > export PATH=/usr/local/openresty/bin:/usr/local/openresty/nginx/sbin:$PATH
    
Instalar y usar lapis

    sudo luarocks install lapis
    sudo luarocks install prtr-dump
    lapis new
    lapis server
    
Instalar Sailor

    $ sudo luarocks install xavante
    $ git clone https://github.com/sailorproject/sailor
    $ cd sailor
    $ sudo luarocks make rockspecs/sailor-current-1.rockspec
    $ sailor create "my app"
    $ cd my_app/
    $ lua start-server.lua
    
Añadir Openresty a Sailor, para esto dentro del proyecto de sailor:

    $ nginx -p `pwd`/ -c conf/nginx.conf 
    $ nginx -p `pwd`/ -c conf/nginx.conf  -s reload
    
Adems hay que crear una carpeta llamada logs y crear dos archivos, "error.log" y "nginx.pid"
---

#### Fuente

+ http://openresty.org/en/installation.html
+ http://leafo.net/lapis/reference/getting_started.html
+ http://leafo.net/lapis/reference/configuration.html
+ http://piratery.net/dump/
+ http://sailorproject.org/
+ https://github.com/sailorproject/sailor/issues/144#issuecomment-263696439
+ https://github.com/sailorproject/sailor/blob/master/docs/INSTALL_MAC.md#alternative-setup-using-nginx-and-openresty
+ https://www.cyberciti.biz/faq/debian-ubuntu-linux-install-libpcre3-dev/
