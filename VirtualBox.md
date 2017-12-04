# VirtualBox

Editar el archivo '/etc/apt/sources.list' y añadir la siguiente linea:

    deb http://download.virtualbox.org/virtualbox/debian xenial contrib
    
Despues ejecutamos:

    $ wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add - && sudo apt-get update && sudo apt-get install linux-headers-$(uname -r) build-essential virtualbox-5.1 dkms
    
Luego ejecutamos Oracle VM VirtualBox Extension Pack:

    $ cd /tmp
    $ wget http://download.virtualbox.org/virtualbox/5.1.26/Oracle_VM_VirtualBox_Extension_Pack-5.1.26-117224.vbox-extpack
    $ sudo VBoxManage extpack install Oracle_VM_VirtualBox_Extension_Pack-5.1.26-117224.vbox-extpack
    
Añadir el usuario que utilizará virtualbox.

    $ sudo adduser <<usuario>> vboxusers

Editar el archivo '/etc/default/virtualbox' y añadir la siguiente linea:

    VBOXWEB_USER=<<usuario>>

Reiniciar el servicio de VirtualBox:

    $ systemctl enable vboxweb-service
    $ systemctl start vboxweb-service

Instalar PHP y Apache2:

    $ sudo apt-get -y install apache2 libapache2-mod-php7.0 libapr1 libaprutil1 libaprutil1-dbd-sqlite3 libaprutil1-ldap libapr1 php7.0-common php7.0-mysql php7.0-soap php-pear wget unzip
    
Reiniciar el servidor Apache2:

    $ sudo systemctl restart apache2.service
    
Instalar Phpvirtualbox:

    $ cd /tmp
    $ wget https://sourceforge.net/projects/phpvirtualbox/files/phpvirtualbox-5.0-5.zip/download
    $ mv download vbox.zip
    $ unzip vbox.zip
    $ mv phpvirtualbox-5.0-5 phpvbox
    $ sudo mv phpvbox /var/www/html
    $ sudo chown -R www-data:www-data /var/www/html/phpvbox
    $ cd /var/www/html/phpvbox
    $ sudo cp config.php-example config.php
    $ sudo nano config.php
    
El codigo anterior abrira el editor nano. Luego hay que ingrear el siguiente codigo:

    [...]
    /* Username / Password for system user that runs VirtualBox */
    var $username = 'vbox';
    var $password = 'secret';
    [...]
    
Luego reiniciamos la maquina host:

    $ sudo reboot


VBoxManage setproperty websrvauthlibrary null
--- 

Fuentes

+ https://www.pacorabadan.com/2017/08/virtualbox-server-ubuntu-16-04-virtualbox-headless-phpvirtualbox/