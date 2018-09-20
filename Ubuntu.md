# Ubuntu
---

#### Instalación de Programas

Agregar los repositorios:

    $ sudo add-apt-repository -y ppa:webupd8team/brackets && sudo add-apt-repository -y ppa:maarten-baert/simplescreenrecorder && sudo add-apt-repository -y ppa:webupd8team/sublime-text-2 && sudo add-apt-repository -y ppa:webupd8team/atom && sudo add-apt-repository -y ppa:nilarimogard/webupd8 && sudo add-apt-repository -y ppa:webupd8team/atom && sudo add-apt-repository -y ppa:webupd8team/java && sudo add-apt-repository -y ppa:tsvetko.tsvetkov/trusty-backports && sudo add-apt-repository -y ppa:maarten-baert/simplescreenrecorder
    $sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927 
    $ echo "deb http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.2 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.2.list
    
Para instalar los programas que no necesitan configurar nada más que la instlación:

    $ sudo apt-get install -y faenza-icon-theme faience-icon-theme glances audacious filezilla midori ambiance-flat-colors  radiance-flat-colors tomboy chromium-browser vlc gimp inkscape bzr bzr-explorer apache2 php5 libapache2-mod-php5 php5-mysql php5-curl php5-gd php5-intl php-pear php5-imagick php5-imap php5-mcrypt php5-memcache php5-ming php5-ps php5-pspell php5-recode php5-snmp php5-sqlite php5-tidy php5-xmlrpc php5-xsl  php5-xcache php5-xdebug mongodb-org git git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev libmysqlclient-dev git-core curl zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev libmysqlclient-dev nginx lighttpd  python-pip gparted atom textadept pdfshuffler meld codeblocks sublime-text gparted mintstick brackets simplescreenrecorder
    
Para instalar los programas que si necesitan configurar algo durante la instlación:

    $ sudo apt-get install mysql-server mysql-client 
    $ sudo apt-get install phpmyadmin 
    $ sudo apt-get install ubuntu-restricted-extras
    $ sudo apt-get install oracle-java8-installer
    
Adicionalemente en el Centro de Software de Ubuntu instalar los siguientes programas:

+ Mysql Workbench
+ Virtualbox
+ Openshot Video Editor
+ Mahjongg
+ Solitario AisleRiot
+ Apache Tomcat

Los programas a instalar manualmente son:

+ Netbeans 8.0.2
+ Eclipse Mars
+ Master PDF Editor
+ Robomongo
+ StarUML

#### Solución de Bugs

En caso de usar la HPX360, usar los siguientes código para solucionar el bug que impide que la máquina se apague o suspenda:

    $ echo "blacklist dw_dmac" | sudo tee -a /etc/modprobe.d/blacklist.conf
    $ echo "blacklist dw_dmac_core" | sudo tee -a /etc/modprobe.d/blacklist.conf
    
En caso que querer instalar Ubuntu luego de haber instalado Windows 8.1, una vez que corra el Live Session de Ubuntu y no detecte las particiones de Windows, usar el siguiente código en la línea de comandos:

En caso que no funcione el wifi

    $ sudo apt-get install --reinstall bcmwl-kernel-source
    
---

Fuentes:

+ http://askubuntu.com/questions/762198/16-04-lts-wifi-connection-issues
+ https://unix.stackexchange.com/questions/416180/ubuntu-no-wifi-adapter-found
