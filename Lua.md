# TUTORIAL LUA

#### Instalación de Lua5.1

Instalar esta versión ya que es compatible con lapis.

    $ sudo apt-get install lua5.1

#### Instalación de Lapis

Instalar luarocks

    $ sudo apt-get install luarocks

Descarga openresty

    http://openresty.org/en/download.html

Instalar openresty

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

---

#### Fuente

http://openresty.org/en/installation.html
http://leafo.net/lapis/reference/getting_started.html
http://leafo.net/lapis/reference/configuration.html
http://piratery.net/dump/