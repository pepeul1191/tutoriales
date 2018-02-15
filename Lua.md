# TUTORIAL LUA

#### Instalación de Lua5.1

Instalar esta versión ya que es compatible con lapis.

    $ sudo apt-get install lua5.1
    
#### Instalación de Lua5.2    
    
    $ sudo apt-get install lua5.2 liblua5.2-dev

Descargar luarocks de https://keplerproject.github.io/luarocks/releases/

    $ ./configure --lua-version=5.2 --versioned-rocks-dir
    $ make build
    $ sudo make install

Para instalar un rock en luarocks5.2

    $ sudo luarocks-5.2 install lua-cjson

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

### LuaMongo

Instalar el librería de c lua para mongodb

    $ wget https://github.com/mongodb/mongo-c-driver/releases/download/1.2.0/mongo-c-driver-1.2.0.tar.gz
    $ tar -xzf mongo-c-driver-1.2.0.tar.gz
    $ cd mongo-c-driver-1.2.0/
    $ ./configure --prefix=/usr --libdir=/usr/lib64
    $ make
    $ sudo make install
    $ sudo luarocks install mongorover
    
### Lua Mac OSX

Instalar Lua5.1 y LuaRocks desde el tar.gz y luego instalar los siguientes aplicaciones desde los gestores de brew y rudix:

    $ brew install nginx
    $ brew install homebrew/nginx/openresty
    $ sudo rudix install libresssl

Añadir al bash:

    > export PATH=/usr/local/Cellar/openresty/1.11.2.3/bin:/usr/local/Cellar/openresty/1.11.2.3/nginx/sbin:$PATH

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
+ http://mongoc.org/libmongoc/1.2.0/installing.html
+ https://github.com/mongodb-labs/mongorover
+ https://stackoverflow.com/questions/39760619/lua-cannot-find-installed-luarocks-on-ubuntu
