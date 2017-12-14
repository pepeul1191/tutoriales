# VirtualBox

Instalar VirtualBox y Extension Pack

    $ sudo apt-get install dkms build-essential linux-headers-`uname -r`
    $ wget http://download.virtualbox.org/virtualbox/5.1.12/virtualbox-5.1_5.1.12-112440~Ubuntu~xenial_amd64.deb
    $ sudo dpkg -i virtualbox-5.1_5.1.12-112440~Ubuntu~xenial_amd64.deb
    $ sudo apt-get install -f
    $ wget http://download.virtualbox.org/virtualbox/5.1.12/Oracle_VM_VirtualBox_Extension_Pack-5.1.12.vbox-extpack
    $ sudo VBoxManage extpack install ./Oracle_VM_VirtualBox_Extension_Pack-5.1.12.vbox-extpack
    
Añadir el usuario vbox.

    $ sudo groupadd vboxusers
    $ sudo useradd -g vboxusers vbox 
    
Editar el archivo '/etc/default/virtualbox '

    VBOXWEB_USER="vbox"
    VBOXWEB_TIMEOUT=0
    VBOXWEB_LOGFILE="/var/log/vboxwebservice.log"
    VBOXWEB_HOST="<<ip del servidor>>"

Crear el archivo de logs:

    $ sudo touch /var/log/vboxwebservice.log
    $ sudo chown vbox:vboxusers /var/log/vboxwebservice.log 
    
Crear el directorio del usuario vbox

    $ sudo mkdir /home/vbox/.VirtualBox
    $ sudo chown vbox:vboxusers /home/vbox/.VirtualBox 
    
Crear contraseña al usuario vbox

    $ sudo passwd vbox
    
Arrancar el servicio de VirtualBox

    $ sudo service vboxweb-service start 
    
Verificar el estado del servicio

    $ sudo service vboxweb-service status 
    $ sudo netstat -nap | grep vboxwebsrv 
    
Arrancar el servicio de acceso via remoto

    $ vboxwebsrv
    
### Instalar RemoteBox

    $ wget -q -O - http://archive.getdeb.net/getdeb-archive.key | sudo apt-key add -
    $ sudo sh -c 'echo "deb http://archive.getdeb.net/ubuntu xenial-getdeb apps" >> /etc/apt/sources.list.d/getdeb.list'
    $ sudo apt-get update
    $ sudo apt-get install remotebox

--- 

Fuentes

+ https://www.pacorabadan.com/2017/08/virtualbox-server-ubuntu-16-04-virtualbox-headless-phpvirtualbox/
+ http://xmodulo.com/how-to-manage-virtualbox-vms-on-remote-headless-server.html
+ https://askubuntu.com/questions/777308/virtualbox-problem-kernel-module-is-not-loaded
+ http://sysads.co.uk/2016/06/06/how-to-install-remotebox-2-1-tool-on-ubuntu-16-04/